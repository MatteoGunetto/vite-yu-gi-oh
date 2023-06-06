<script >
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import axios from 'axios';
import { store } from './store';
  export default{
    name: 'App',
    components:{
      AppHeader,
      AppMain,
    },
    data(){
      return{
        store
      }
    },
    methods: {
      getMyDeck(){
        axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php')
          .then((response) => {
            console.log(response.data.data.slice(0, 40));
            this.store.deck = response.data.data.slice(0, 40);
          });
      },
      getMyArchetypes(){
        axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php')
          .then((response) => {
            console.log(response.data.slice(0,40));
            this.store.archetypeDeck = response.data.slice(0,40);
          });
      }
    },
    created() {
      this.getMyDeck();
      this.getMyArchetypes()
    },
    computed: {
    }
  }
</script>

<template>
  <AppHeader/>
  <AppMain />

</template>

<style lang="scss">
  @import '../src/styles/main.scss';
</style>