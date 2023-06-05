<script >
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import AppFooter from './components/AppFooter.vue';
import axios from 'axios'
  export default{
    name: 'App',
    components:{
      AppHeader,
      AppMain,
      AppFooter
    },
    created() {
      axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php')
      .then((response) => {
        
      }
      );
    }
  }
</script>
<template>
  <AppHeader/>
  <AppMain />
  <AppFooter />
  
</template>

<style lang="scss">
  @import '../src/styles/main.scss';
</style>