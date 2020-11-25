<template>
    <div v-if="character">
        <h2>Name:{{character.name}}</h2>
        <p>Status:{{character.status}}</p>
        <p>Species:{{character.species}}</p>
        <p>Gender:{{character.gender}}</p>
        <p>Origin:{{character.origin.name}}</p>
        <img src="character.image" alt="">
    </div>
    <div v-else>
        <p>Pick a Character!</p>
    </div>
</template>

<script>
export default {
    name: 'character-detail',
    props: ['character']
}
</script>

<style>

</style>