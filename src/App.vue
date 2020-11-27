<template>
  <div class="container mt-4">
    <app-note-status :notesCount="notes.length" :maxNotes="maxNotes"></app-note-status>
    <hr>
    <app-new-note @noteAdded="noteAdd"></app-new-note>
    <hr>
    <app-note-view :notes="notes"></app-note-view>
  </div>
</template>

<script>
import Notes from './components/NotesView.vue';
import NewNote from './components/NewNote.vue';
import NoteStatus from './components/NoteStatus.vue';
import { eventBus } from './main.js';
export default {
  data () {
    return {
      notes: [
        "It's my first note"
      ],
      maxNotes: 10
    }
  },
  methods: {
    noteAdd (quote) {
      if (this.notes.length >= 10) {
        return alert('Note Limit Exceed!');
      }
      this.notes.push(quote);
    }
  },
  components: {
    appNoteView: Notes,
    appNewNote: NewNote,
    appNoteStatus: NoteStatus
  },
  created () {
      eventBus.$on('deleteNote', (index) => {
          this.notes.splice(index, 1);
      });
  }
}
</script>

<style>

</style>
