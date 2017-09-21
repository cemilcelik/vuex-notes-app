<template>
    <div id="toolbar">
        <a href="#" @click="addNote">E</a>
        <a href="#" @click="toggleFavorite">F</a>
        <a href="#" @click="deleteNote">D</a>
    </div>
</template>

<script>
    import { addNote, deleteNote, toggleFavorite } from '../vuex/actions';

    export default {
        vuex: {
            getters: {
                activeNote: state => state.activeNote
            },
            actions: {
                addNote,
                deleteNote,
                toggleFavorite
            }
        }
    }
</script>

<style>

</style>
