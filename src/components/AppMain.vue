<script>
import { store } from '../store';
    export default {
        name: 'AppMain',
        data(){
            return{
                store
            }
        }
    }
</script>
<template>
    <main class="min-vh-100 py-4">
        <div class="container overflow-hidden">
            <div class="row gx-2">
                <div class="col-auto mb-3">
                    <select name="archetype" id="archetype">
                        <option v-for="element in store.archetypeDeck" :value="element">{{ element.archetype_name }}</option>
                    </select>
                </div>
            </div>
            <div class="row my-card-container py-3 px-4 gx-2">
                <div class="col-12 bg-dark p-1">
                    <h3 class="text-white">
                        Found
                        <span> {{ store.deck.length }}</span>
                        cards
                    </h3>
                </div>
                <div class="single-card text-center pb-2" v-for="element in store.deck">
                    <img :src="element.card_images[0].image_url" :alt="element.name">
                    <h5 class="text-white text-uppercase">
                        {{ element.name }}
                    </h5>
                    <span> {{ element.archetype }}</span>
                </div>
            </div>
        </div>
    </main>
</template>
<style lang="scss" scoped>
@use '../styles/main.scss' as *;
    main{
        background-color: $my-primary-color;
    }
    div.my-card-container{

        background-color: white;
    }
    div.single-card{
        width: calc(100% / 5);
        background-color: $my-primary-color;
        border-bottom: 15px white solid;
        img{
            height: 300px;
        }
    }
</style>