<template>
    <div class="pokemon-container">
        <img :src="imgSrc"
            class="hidden-pokemon"
            alt="imgPokemon">
        <img v-if="showPokemon"
            :src="imgSrc"
            class="fade-in"
            alt="imgPokemon">
    </div>
</template>

<script>
export default {
    props: {
        pokemonId: {
            type: Number,
            required: true
        },
        showPokemon: {
            type: Boolean,
            required: true,
            default: false
        }
    },
    computed: {
        imgSrc(){
            return `https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/dream-world/${this.pokemonId}.svg`
        }
    }
}
</script>

<style scoped>
/* Pokemon Picture */
.hidden-pokemon {
    filter: grayscale(100%) brightness(0%);
}
.pokemon-container {
    position: relative;
    height: 200px;
}
img {
    height: 200px;
    position: absolute;
    right: 0%;
    width: 100vw;
    user-select: none;
    -moz-user-select: none;
    -ms-user-select: none;
    -webkit-user-drag: none;
    -webkit-user-select: none;
}


</style>