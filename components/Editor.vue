 <template>
    <div id="editor">
        <textarea name="text" id="text" class="form-control" @input="editNote" :value="activeNoteText"></textarea>
    </div>
 </template>
 
 <script>
    import { editNote } from '../vuex/actions';
    
    export default {
        vuex: {
            getters: {
                activeNoteText: state.activeNote.text
            },
            actions: {
                editNote
            }
        }
    }
 </script>
 
 <style>
 
 </style>
 