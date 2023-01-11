<template>
    <main class="m-3">
        <div class="container my-background">
            <div class="row g-4">
                <div class="col-12 bg-dark">
                    <p class="fs-5  text-white">Found {{ store.cardsList.length }} cards</p>
                </div>
                <div class="col-6 col-md-4 col-lg-3 d-flex" v-for=" card in store.cardsList">
                    <div class="card text-bg-white mb-3">
                        <img :src="card.card_images[0].image_url" :alt="card.name">
                        <div>
                            <h6 class=" text-center">{{ card.name }}</h6>
                            <p class="text-center">{{ card.archetype }}</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </main>
</template>
<script>
import { store } from '../store.js';
export default {
    name: "AppMain",
    data() {
        return {
            store
        };
    },

}
</script>
<style lang="scss" scoped>


.my-background{
    background-color: orange;
}
</style>