<template>
    <div class="page">
      <Header :showRegistration="showRegistration"></Header>
      <Main></Main>
      <Footer></Footer>
      <transition name="fade">
        <UserRegistration v-model:show="registrationVisible"></UserRegistration>
    </transition>
    </div>
</template>

<script>
import Header from './components/Header.vue';
import Main from './components/main/Main.vue';
import Footer from './components/Footer.vue';
import UserRegistration from './components/UserRegistration.vue';
export default {
  components: {
    Header, Main, Footer, UserRegistration
  },
  name: 'App',
  data() { 
    return{
      registrationVisible: false
    }
  },
  methods: {
    showRegistration() {
      this.registrationVisible = true;
      document.body.style.overflow = 'hidden';
    }
  }
  
}
</script>

<style>
  *{
    margin: 0;
    padding: 0;
    font-family: 'Merienda', cursive;
  }
  ._container{
    width: 1462px;
    margin: 0 auto;
  }
  .page{
      overflow: hidden;
  }
  .fade-enter-active, .fade-leave-active {
      transition: opacity .5s;
    }
  .fade-enter-from, .fade-leave-to {
      opacity: 0;
    }
</style>
