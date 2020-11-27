<template>
    <div class="row">
        <app-note v-for="(note, index) in notes" :index="index" :key="note">{{ note }}</app-note>
    </div>
</template>

<script>
import Note from './Note.vue';
export default {
    props: ['notes'],
    components: {
        appNote: Note
    }
}
</script>