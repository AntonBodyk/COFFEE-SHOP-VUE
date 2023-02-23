<template>
    <footer class="footer">
        <div class="footer-container _container">
            <div class="footer-info">
            <div class="footer-logo">
                <img src="../assets/img/coffee-beans.png" alt="">
            </div>
            <ul class="footer-list">
                <li><a href="#">Coffee house</a></li>
                <li><a href="#">Our coffee</a></li>
                <li><a href="#">For your pleasure</a></li>
            </ul>
        </div>
        <div class="main-coffee-components">
            <img src="../assets/img/Line-1.png" alt="">
            <img src="../assets/img/Group-2.png" alt="">
            <img src="../assets/img/Line-1.png" alt="">
        </div>
    </div>
</footer>
</template>
 
<script>
    export default {
        data() {
            return{}
        }
    }
</script>
 
<style scoped>
.footer{
    text-align: center;
    font-family: 'Merienda', cursive;
}
.footer-container{
    padding-top: 30px;
}
.footer-info{
    display: flex;
    justify-content: center;
}
.footer-list{
    display: flex;
    list-style-type: none;
    margin: 15px 0 0 -40px;
}
.footer-list li{
    margin-left: 40px;
}
.footer-list a{
    font-size: 12px;
    color: #000000;
    text-decoration: none;
}
.main-coffee-components img{
    padding-top: 20px;
    margin: 0 0 35px 20px;
}
.main-coffee-components img:first-child{
    margin-left: 0;
    padding-bottom: 15px;
}
.main-coffee-components img:last-child{
    padding-bottom: 15px;
}
</style>