<template>
    <div class="page">
      <Header></Header>
      <Main></Main>
      <Footer></Footer>
    </div>
</template>

<script>
import Header from './components/Header.vue';
import Main from './components/main/Main.vue';
import Footer from './components/Footer.vue';
export default {
  components: {
    Header, Main, Footer
  },
  name: 'App'
  
}
</script>

<style>
  *{
    margin: 0;
    padding: 0;
  }
  ._container{
    width: 1462px;
    margin: 0 auto;
  }
  .page{
      overflow: hidden;
  }
</style>
