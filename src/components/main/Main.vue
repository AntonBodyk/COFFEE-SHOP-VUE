<template>
    <main class="main">
        <div class="main-container">
            <MainInfo :showModal="showModal" :modalVisible="modalVisible"></MainInfo>
            <MainAboutUs></MainAboutUs>
            <MainOurBest></MainOurBest>
            <MainSales></MainSales>
            <transition name="fade">
                <MainModal v-model:show="modalVisible"></MainModal>
            </transition>
        </div>
    </main>
</template>
 
<script>
import MainInfo from './MainInfo.vue';
import MainAboutUs from './MainAboutUs.vue';
import MainOurBest from './MainOurBest.vue';
import MainSales from './MainSales.vue';
import MainModal  from './MainModal.vue';
    export default {
        components: {
            MainInfo, MainAboutUs, MainOurBest, MainSales, MainModal
        },
        data() {
            return {
                modalVisible: false,
            }
        },
        methods: {
            showModal() {
                this.modalVisible = true;
                document.body.style.overflow = 'hidden';
            }
        }
    }
</script>
 
<style scoped>
    .main{
        font-family: 'Merienda', cursive;
        text-align: center;
        margin-top: -400px;
    }

    .fade-enter-active, .fade-leave-active {
        transition: opacity .5s;
    }
    .fade-enter-from, .fade-leave-to {
        opacity: 0;
    }
</style>