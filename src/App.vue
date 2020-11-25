<template>
  <div>
    <h1>Hello Rick and Morty</h1>
    
    <characters-list :charactersList="charactersList"></characters-list>
    <character-detail :character="selectedCharacter"></character-detail>

  </div>
</template>

<script>
import charactersList from './components/charactersList.vue';
import characterDetail from './components/characterDetail.vue';
import { eventBus } from './main.js';

export default {
  name: 'app',
  data() {
    return {
      charactersList: [],
      selectedCharacter: null
    };
  },
  mounted(){
    fetch('https://rickandmortyapi.com/api/character/')
    .then(response => response.json())
    .then(charactersList => this.charactersList = charactersList.results)
    eventBus.$on('character-selected', (character) => {
      this.selectedCharacter = character;
    })
  },
  components: {
    'characters-list': charactersList,
    'character-detail': characterDetail
  }
}
</script>

<style>

</style>