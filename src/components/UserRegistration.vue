<template>
    <div class="modal" v-if="show">
        <div class="modal__dialog">
            <div class="modal__content">
                <form @submit="validationForm">
                    <div @click="hideModal" class="modal__close">&times;</div>
                    <div class="modal__title">Регистрация пользователя</div>
                    <input required v-model="form.email" placeholder="Введите email" name="name" type="email" class="modal__input">
                    <input required v-model="form.password" v-show="!showPassword" placeholder="Введите пароль" name="password" type="password" class="modal__input">
                    <input required v-model="form.password" v-show="showPassword" placeholder="Введите пароль" name="password" type="text" class="modal__input">
                    <div class="show-password">
                        <input type="checkbox" @click="showPassword = !showPassword">
                        <span>Показать пароль</span>
                    </div>
                    <button type="submit" class="btn btn_dark btn_min">Зарегистрироваться</button>
                </form>
            </div>
        </div>
    </div>
</template>
 
<script>
import modalMixin from './mixins/modalMixin';

    export default {
        mixins: [modalMixin],
        data(){
            return {
                form: {
                    email: "",
                    password: ""
            },
            showPassword: false
        }
        },
        methods: {
           async validationForm(e) {
                e.preventDefault();
                if (this.form.password.length < 3) return;

                await fetch("assets/server.php", {
                method: "POST",
                headers: {
                    "Content-Type": "application/json"
                },
                body: JSON.stringify(this.form)
            })
                .then(function (response) {
                    console.log( response);
                    
            })
                .catch(function (error) {
                    console.error(error);
                
            })
                .finally(() => {
                    this.hideModal();
                    this.form = {
                        email: "",
                        password: ""
                };
            });
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
.show-password{
    display: flex;
    margin-left: 90px;
}
.show-password span{
    color: grey;
    font-size: 12px;
    padding-left: 5px;
}
.btn{
    display:block;
    width:250px;
    height: 50px;
    border-radius: 5px;
    border: none;
    margin:0 auto;
    margin-top: 15px;
    background-color: black;
    color: #fff;
    font-size:18px;
    cursor: pointer;
}
</style>