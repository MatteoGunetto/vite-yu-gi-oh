<script>
    export default {
        name: 'AppMain'
    }
</script>

<template>

    <main class="vh-100 py-4">

        <div class="container">
            <div class="mb-3">
                <select name="archetype" id="archetype">
                    <option value="alien">Alien</option>
                </select>
            </div>
            <div class="my-card-container d-flex flex-wrap justify-content-around align-items-start py-3 px-4">
                <div class="single-card text-center p-3">
                    <img src="https://m.media-amazon.com/images/I/51n9U3qo-iL._AC_.jpg" alt="">
                    <h5 class="text-white text-uppercase">nome carta</h5>
                    <span> race carta</span>
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
        background-color: $my-primary-color;
        img{
            height: 400px;
        }
    }
</style>