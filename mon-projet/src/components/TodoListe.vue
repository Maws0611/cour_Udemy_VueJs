<template>
    <div>
        <h5 class="bg-dark text-light d-flex justify-content-center">La To-Do Liste!</h5>
        <form class="container">
            <h1 class="mt-5">Rentrez vos choses à faire.</h1>
            <div class="mb-3">
                <label for="action" class="form-label">Action</label>
                <input v-model="formData.tache" type="text" class="form-control" id="action">
            </div>
            <button class="btn btn-primary my-3">Créer une tâche</button>
        </form>
                <iteme v-bind:tache="task"></iteme>
        <ul>
            <li v-bind:key="index" v-for="(task, index) in tableauTache">
                <iteme v-bind:tache="task"></iteme>
            </li>
        </ul>
    </div>
</template>

<script>
import ItemApp from './ItemApp'

    export default {
        name: 'todoListe',
        data(){
            return{
                formData: {
                    tache: ''
                },
                tableauTache: ['java', 'Php', 'Javascript']
            }
        },
        component: {
            'iteme' : ItemApp
        },
        methods: {
            ajoutTache: function(){
                
            },
            deleteTache: function(){

            }
        }
    }
</script>

<style scoped>

</style>