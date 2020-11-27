<template>
    <div class="col-sm-6 col-md-4 col-lg-3 mt-2">
        <div class="card">
            <span class="deteleBtn" @click="deleteItem(index)">&times;</span>
            <div class="card-body">
                <slot></slot>
            </div>
        </div>
    </div>
</template>

<script>
import { eventBus } from '../main.js';
export default {
    props: ['index'],
    methods: {
        deleteItem (index) {
            eventBus.$emit('deleteNote', this.index)
        }
    }
}
</script>
<style scoped>
    .deteleBtn {
        position: absolute;
        top: .5rem;
        right: .5rem;
        color: #dc3545;
        cursor: pointer;
        height: 20px;
        width: 20px;
        border-radius: 50%;

        display: flex;
        justify-content: center;
        align-items: center;
    }
    .deteleBtn:hover {
        background-color: #f8f9fa;
    }
</style>