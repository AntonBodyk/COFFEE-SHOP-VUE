<template>
    <div class="promotion__timer _container">
        <h2>Spring discounts on our products -15%</h2>
            <div class="title">Left until the end of the promotion:</div>
            <div class="timer">
                <div class="timer__block">
                    <span id="days">{{ days }}</span>
                        days
                </div>
                <div class="timer__block">
                    <span id="hours">{{ hours }}</span>
                    hours
                </div>
                <div class="timer__block">
                    <span id="minutes">{{ minutes }}</span>
                    minutes
                </div>
                <div class="timer__block">
                    <span id="seconds">{{ seconds }}</span>
                    seconds
                </div>
            </div>
        </div>
</template>
 
<script>
    export default {
        data() {
            return {
                days: 0,
                hours: 0,
                minutes: 0,
                seconds: 0,
                loaded: false,
                launchDate: new Date('30 May 2023')
            }
        },
        computed: {
            _seconds: () => 1000,
            _minutes() {
                return this._seconds * 60;
            },
            _hours() {
                return this._minutes * 60;
            },
            _days() {
                return this._hours * 24;
            }
        },
        mounted(){
            this.showRemaining();
        },
        methods: {
            formatNumb(num) {
                return num < 10 ? `0${num}` : num;
            },
            showRemaining() {
                const timer = setInterval(() => {
                const currDate = new Date();
                const deadlineTime = this.launchDate - currDate;

                if(deadlineTime < 0) {
                    clearInterval(timer);
                    return;
                }

                const days = Math.floor((deadlineTime / this._days));
                const hours = Math.floor((deadlineTime % this._days) / this._hours);
                const minutes = Math.floor((deadlineTime % this._hours) / this._minutes);
                const seconds = Math.floor((deadlineTime % this._minutes) / this._seconds);

                this.minutes = this.formatNumb(minutes);
                this.seconds = this.formatNumb(seconds);
                this.hours = this.formatNumb(hours);
                this.days = this.formatNumb(days);
                this.loaded = true;
            }, 1000);
        }
    }
}
</script>
 
<style scoped>
.promotion__timer{
    margin: 30px 0 100px 0;
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