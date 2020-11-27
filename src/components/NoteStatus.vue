<template>
    <div>
        <h4>Added Note</h4>
        <div class="progress" style="height: 25px;">
            <div class="progress-bar progress-bar-striped progress-bar-animated" role="progressbar" :style="{width: (notesCount / maxNotes) * 100 + '%'}" aria-valuenow="25" aria-valuemin="0" aria-valuemax="100">
                {{ notesCount }} / {{ maxNotes }}
            </div>
        </div>
    </div>
</template>
<script>
export default {
    props: ['notesCount', 'maxNotes']
}
</script>