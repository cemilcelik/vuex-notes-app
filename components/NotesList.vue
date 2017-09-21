<template>
    <div id="notes-list">
        <div class="button-group">
            <div class="button-group">
                <button @click="show = 'all'" :class="{ active: show === 'all' }">All</button>
            </div>
            <div class="button-group">
                <button @click="show = 'favorite'" :class="{ active: show === 'favorite' }">Favorites</button>
            </div>
        </div>
        <ul>
            <li v-for="note in filteredNotes">
                <a href="#" @click="updateActiveNote(note)">{{ note.text }}</a>
            </li>
        </ul>
    </div>
</template>

<script>
    import { updateActiveNote } from '../vuex/actions';

    export default {
        data() {
            return {
                show: 'all'
            }
        },
        vuex: {
            getters: {
                notes: state.notes,
                activeNote: state.activeNote
            },
            actions: {
                updateActiveNote
            }
        },
        computed: {
            filteredNotes() {
                if (this.show === 'all') {
                    return this.notes;
                }else{
                    return this.notes.filter(note => note.favorite)
                }
            }
        }
    }
</script>

<style>

</style>
