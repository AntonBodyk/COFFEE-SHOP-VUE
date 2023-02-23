<template>
    <div class="main-info _container">
        <h1>Everything You Love About Coffee</h1>
        <div class="main-coffee-components">
            <img src="../../assets/img/Line.png" alt="">
            <img src="../../assets/img/Group-1.png" alt="">
            <img src="../../assets/img/Line.png" alt="">
        </div>
        <p>We makes every day full of energy and taste</p>
        <p>Want to try our beans?</p>
        <a href="#" class="btn">More</a>
    </div>
</template>
 
<script>
    export default {
        
    }
</script>
 
<style scoped>
.main-info{
    text-align: center;
}
.main-info h1{
    font-weight: bold;
    color: #FFFFFF;
    font-size: 40px;
    text-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
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
.main-info p{
    font-weight: 700;
    color: #FFFFFF;
    font-size: 24px;
    line-height: 35px;
}
.main-info p:last-child{
    padding-top: 20px;
}
.btn{
    display: block;
    width: 120px;
    height: 30px;
    border: 1px solid #FFFFFF;
    filter: drop-shadow(0px 4px 4px rgba(0, 0, 0, 0.25));
    border-radius: 3px;
    padding-top: 5px;
    color: #FFFFFF;
    text-decoration: none;
    margin: 18px 0 0 665px;
}
</style>