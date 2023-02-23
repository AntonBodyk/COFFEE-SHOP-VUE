<template>
    <main class="main">
        <div class="main-container">
            <MainInfo></MainInfo>
            <MainAboutUs></MainAboutUs>
            <MainOurBest></MainOurBest>
            <MainSales></MainSales>
        </div>
    </main>
</template>
 
<script>
import MainInfo from './MainInfo.vue';
import MainAboutUs from './MainAboutUs.vue';
import MainOurBest from './MainOurBest.vue';
import MainSales from './MainSales.vue';
    export default {
        components: {
            MainInfo, MainAboutUs, MainOurBest, MainSales
        }
    }
</script>
 
<style scoped>
    .main{
        font-family: 'Merienda', cursive;
        text-align: center;
        margin-top: -400px;
    }
</style>