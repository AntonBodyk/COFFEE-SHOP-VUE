<template>
    <header class="header">
            <div class="header-container _container">
                <div class="header-logo">
                    <img src="../assets/img/Group.png" alt="sorry">
                </div>
                <nav class="header-menu">
                    <ul>
                        <li><a href="#">Coffee house</a></li>
                        <li><a href="#">Our coffee</a></li>
                        <li><a href="#">For your pleasure</a></li>
                    </ul>
                </nav>
                <div class="header-buttons">
                    <fa icon="circle-user" class="fa-solid" @click="this.showRegistration"/>
                    <fa icon="cart-shopping" class="fa-solid"/>
                </div>
            </div>
        </header>
</template>
 
<script>
    export default {
        props: {
            showRegistration: {
                type: Function
            }
        }
    }
</script>
 
<style scoped>
.header{
    font-family: 'Merienda', cursive;
    background: url('../assets/img/desk.png') center center/cover no-repeat;
    height: 640px;
}
.header-container{
    display: flex;
}
.header-logo{
    padding: 30px 0 0 149px;
}
.header-logo img{
    height: 45px;
    width: 45px;
}
.header-menu ul{
    display: flex;
    list-style-type: none;
    padding: 48px 0 0 5px;
}
.header-menu li{
    margin-left: 40px
}
.header-menu li:first-child{
    margin-left: -10px;
}
.header-menu a{
    color: #FFFFFF;
    font-size: 12px;
    text-decoration: none;
}
.header-buttons{
    display: flex;
    margin: 50px 0 0 700px;
}
.fa-solid{
    height: 25px;
    color: #FFFFFF;
    cursor: pointer;
    margin-left: 20px;
}
</style>