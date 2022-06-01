<template>
    <div class="container">
        <h1>{{txt}}</h1>
        <h2>Developper avec vue c'est top</h2>
    <div v-on:click="component='text1'" class="btn btn-outline-primary me-2">Onglet 1</div>
    <div v-on:click="component='text2'" class="btn btn-outline-primary ">Onglet 2</div>
    <div class="card mb-5" >
        <component v-bind:is="component"></component>
    </div>
 
    <modaleapp v-bind:revel="revel" v-bind:toggleModal="toggleModal"></modaleapp>
    <div v-on:click="toggleModal" class="btn btn-success mb-5">ouvrir le modal</div>

    
    <formulaire></formulaire>
    </div>
</template>

<script>
import FormulaireApp from "./FormulaireApp"

import Text1App from './Text1App'
import Text2App from './Text2App'
import ModaleApp from './ModaleApp'

export default {
    name: 'ContenueApp',
    data(){
        return {
            txt: 'My first application',
               toggle1:true,
               toggle2:false,
               component:'text1',
               revel: false,
               
            }
    },
    components: {
        'text1': Text1App,
        'text2': Text2App,
        'modaleapp': ModaleApp,
        'formulaire' : FormulaireApp,
    },
    methods:{
        onglet1: function(){
            this.toggle1=true
            this.toggle2=false
        },
        onglet2: function(){
            this.toggle1=false
            this.toggle2=true
        },
        toggleModal: function(){
            this.revel=!this.revel
        }
    }
    
}
</script>

<style scoped>
.api{
    color: white;
}
</style>