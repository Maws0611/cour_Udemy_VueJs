<template>
    <div>
        <div class="card my-2 item-todo">
            <p>{{ tache }}</p>
            <div class=" d-flex justify-content-end ">
                <button v-on:click="deleteTache" class="btn-suppr btn btn-danger">X</button>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'itemApp',
        props: ['tache', 'deleteTache'],
        
    }
</script>

<style scoped>
    .item-todo{
        font-size: 20px;
    }
</style>