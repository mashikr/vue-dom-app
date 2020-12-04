<template>
    <div class="card-columns">
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

<style scoped>
    @media (min-width: 576px) {
        .card-columns {
            -webkit-column-count: 2;
            -moz-column-count: 2;
            column-count: 2;
        }
    }

    @media (min-width: 1200px) {
        .card-columns {
            -webkit-column-count: 3;
            -moz-column-count: 3;
            column-count: 3;
        }
    }
</style>