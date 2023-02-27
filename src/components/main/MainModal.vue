<template>
     <div class="modal" v-if="show">
        <div class="modal__dialog">
            <div class="modal__content">
                <form @submit="PostForm">
                    <div @click="hideDialog" class="modal__close">&times;</div>
                    <div class="modal__title">Мы свяжемся с вами как можно быстрее!</div>
                    <input required v-model="form.name" placeholder="Ваше имя" name="name" type="text" class="modal__input">
                    <input required v-model="form.phone" placeholder="Ваш номер телефона" name="phone" type="phone" class="modal__input">
                    <button type="submit" class="btn btn_dark btn_min">Перезвонить мне</button>
                </form>
            </div>
        </div>
    </div>
</template>
 
<script>
    export default {
        props:{
            show: {
                type: Boolean,
                default: false
            }
        },
        data() {
            return{
                form: {},
                message: {
                    loading: 'Загрузка...',
                    success: 'Спасибо! Скоро мы с вами свяжемся',
                    failure: 'Что-то пошло не так...'
                }
            }
        },
        methods: {
            hideDialog() {
                this.$emit('update:show', false);
                document.body.style.overflow = '';
            },
            async PostForm(e) {
                e.preventDefault();

                await fetch('assets/server.php', {
                    method: 'POST',
                    headers: {
                        'Content-Type': 'application/json'
                    },
                    body: JSON.stringify(this.form)
                })
                .then(
                    function(response, message) {
                        console.log('Ответ сервера', response);
                        const thanksModal = document.createElement('div');
                        thanksModal.classList.add('modal__dialog');
                        thanksModal.innerHTML = `
                                <div class="modal__content">
                                    <div class="modal__close" data-close>&times;</div>
                                    <div class="modal__title">${message}</div>
                                </div>
                            `;
                    }
                )
                .catch(
                    function(error) {
                        console.error(error);
                    }
                )
                .finally(() => {
                    this.hideDialog();
                })
            }
    }
}
</script>
 
<style scoped>
.modal{
    position:fixed;
    top:0;
    left:0;
    z-index:1050;
    
    width:100%;
    height:100%;
    overflow:hidden;
    background-color:rgba(0,0,0,.5);
}
.modal__dialog{
    max-width:500px;
    margin:40px auto;
    padding-right: 80px;
}
.modal__content{
    position:relative;
    width:100%;
    padding:40px;
    background-color:#fff;
    border:1px solid rgba(0,0,0,.2);
    border-radius:4px;
    max-height:80vh;
    overflow-y:auto;
}
.modal__close{
    position:absolute;
    top:8px;
    right:14px;
    font-size:30px;
    color:#000;
    opacity:.5;
    font-weight:700;
    border:none;
    background-color:transparent;
    cursor:pointer;
}
.modal__title{
    text-align:center;
    font-size:22px;
    text-transform:uppercase;
}
.modal__input{
    display:block;
    margin:20px auto 20px auto;
    width:280px;
    height:50px;
    background:#fff;
    box-shadow:0 4px 15px rgba(0,0,0,.2);
    border:none;
    font-size:18px;
    text-align:center;
    padding:0 20px;
    outline:0;
}
.btn{
    display:block;
    width:250px;
    height: 50px;
    border-radius: 5px;
    border: none;
    margin:0 auto;
    background-color: black;
    color: #fff;
    font-size:18px;
    cursor: pointer;
}
</style>