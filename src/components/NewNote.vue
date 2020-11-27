<template>
    <div class="row justify-content-center">
        <div class="col-sm-8 col-md-6">
            <form>
                <div class="form-group">
                    <label for="note">Note</label>
                    <textarea name="note" rows="3" class="form-control" v-model="quote"></textarea>
                    <button class="btn btn-primary mt-2" @click.prevent="createNew">Add Note</button>
                </div>

            </form>
        </div>
    </div>
</template>

<script>
export default {
    data: function () {
        return {
            quote: ''
        }
    },
    methods: {
        createNew () {
            if (this.quote) {
                this.$emit('noteAdded', this.quote);
                this.quote = '';
            } else {
                alert('Write Somethong!')
            }
        }
    }
}
</script>