<template>
    <div class="promotion__timer _container">
        <h2>Spring discounts on our products -15%</h2>
            <div class="title">Left until the end of the promotion:</div>
            <div class="timer">
                <div class="timer__block">
                    <span id="days">30</span>
                        days
                </div>
                <div class="timer__block">
                    <span id="hours">20</span>
                    hours
                </div>
                <div class="timer__block">
                    <span id="minutes">56</span>
                    minutes
                </div>
                <div class="timer__block">
                    <span id="seconds">20</span>
                    seconds
                </div>
            </div>
        </div>
</template>
 
<script>
    export default {

    }
</script>
 
<style scoped>
.promotion__timer{
    margin: 30px 0;
    width: 1000px;
}
.promotion__timer h2{
    margin-left: 500px;
}
.promotion__timer .title{
    margin: 10px 0 0 500px;
}
.promotion__timer .timer{
    margin-top:60px;
    padding-left:95px;
    display:flex;
    margin-left: 350px;
}
.promotion__timer .timer__block{
    width:102px;
    height:130px;
    margin-left: 50px;
    background:#fff;
    box-shadow:0 4px 20px rgba(0,0,0,.25);
    font-size:16px;
    font-weight:300;
    text-align:center;
}
.promotion__timer .timer__block span{
    display:block;
    margin-top:20px;
    margin-bottom:5px;
    font-size:56px;
    font-weight:700;
}
</style>