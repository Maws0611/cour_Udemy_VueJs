<template>
    <div>
        <div v-on:click="component='text1'" class="btn btn-outline-primary me-2">Onglet 1</div>
        <div v-on:click="component='text2'" class="btn btn-outline-primary ">Onglet 2</div>
        <div class="card mb-5" >
            <component v-bind:is="component"></component>
        </div>
    </div>
</template>

<script>
import Text1App from './Text1App'
import Text2App from './Text2App'

export default {
    name: 'navigationApp',
    data(){
        return {
            txt: 'My first application',
               component:'text1'
            }
    },
    components: {
        'text1': Text1App,
        'text2': Text2App,
    },
    methods:{
        onglet1: function(){
            this.toggle1=true
            this.toggle2=false
        },
        onglet2: function(){
            this.toggle1=false
            this.toggle2=true
        }
    }
    
}
</script>

<style scoped>

</style>