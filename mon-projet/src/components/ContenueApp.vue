<template>
    <div class="">
        <!-- <h1>{{txt}}</h1>
        <h2>Developper avec vue c'est top</h2>
    <navigation></navigation>
    <modaleapp v-bind:revel="revel" v-bind:toggleModal="toggleModal"></modaleapp>
    <div v-on:click="toggleModal" class="btn btn-success mb-5">ouvrir le modal</div>
    <formulaire></formulaire> -->
    <!-- <todoliste></todoliste> -->
<h5 class="bg-dark text-light d-flex justify-content-center">La To-Do Liste!</h5>
        <form class="container">
            <h1 class="mt-5">Rentrez vos choses à faire.</h1>
            <div class="mb-3">
                <label for="action" class="form-label">Action</label>
                <input v-model="formData.tache" type="text" class="form-control" id="action">
            </div>
            <button v-on:click.prevent="creationItem" class="btn btn-primary my-3">Créer une tâche</button>
        </form>
                
        <ul>
            <li v-bind:key="index" v-for="(task, index) in tableauTache">
                <item v-bind:id="index" v-bind:tache="task" v-bind:deleteTache="deleteTache"></item>
            </li>
        </ul>
    </div>
</template>

<script>
import ItemApp from './ItemApp'
// import FormulaireApp from "./FormulaireApp"
// import NavigationApp from './NavigationApp'
// import ModaleApp from './ModaleApp'
// import TodoListe from './TodoListe'

export default {
    name: 'ContenueApp',
    data(){
        return {
            // txt: 'My first application',
            //    toggle1:true,
            //    toggle2:false,
            //    revel: false
            formData: {
                    tache: ''
                },
                tableauTache: ['java', 'Php', 'Javascript']
            }
    },
    components: {
        // 'navigation': NavigationApp,
        // 'modaleapp': ModaleApp,
        // 'formulaire' : FormulaireApp,
        // 'todoliste' : TodoListe
        'item' :ItemApp
    },
    methods:{
        toggleModal: function(){
            this.revel=!this.revel
        },
        creationItem: function(){
            this.tableauTache.push(this.formData.tache)
            this.formData.tache=''
        },
        deleteTache: function(e){
            this.tableauTache.splice(e.target.parentNode.id, 1)
        }
    }
    
}
</script>

<style scoped>

</style>