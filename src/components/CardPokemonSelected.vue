<script setup>
const pokemon = defineProps(["name", "xp", "height", "image", "loading"])


</script>

<template>
    <div class="card CardPokemonSelected " :class="pokemon.loading ? '' : 'animate__animated animate__flipInY'">

        <img v-if="pokemon.name" :src="pokemon.image" class="card-img-top pt-2" :alt="pokemon.name" height="250">
        <img v-else src="../assets/egg_pokemon.svg" class="card-img-top pt-2" alt="???" height="250">

        <div class="card-body">
            <h5 class="card-title text-center"> {{ pokemon.name || '???' }} </h5>
            <hr>
            <div class="row">
                <section class="col">
                    <strong>XP:</strong>
                    <span> {{ pokemon.xp }} </span>
                </section>
                <section class="col">
                    <strong>Altura:</strong>
                    <span> {{ pokemon.height }} </span>
                </section>
            </div>
        </div>
    </div>
</template>


<style scoped>
.CardPokemonSelected {
    height: 75vh;
    background: rgb(63, 94, 251);
    background: radial-gradient(circle, rgb(216, 208, 95) 0%, rgba(252, 91, 70, 0.8) 100%);
    cursor: pointer;
}
</style>