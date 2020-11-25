<template>
    <div>
        <ul>
            <list-item v-for="(character, index) in charactersList" :character="character" :key="index"></list-item>
        </ul>
    </div>
</template>

<script>
import listItem from './listItem.vue'

export default {
    name: 'characters-list',
    props: ['charactersList'],
    components: {
        'list-item': listItem
    }

}
</script>

<style>

</style>