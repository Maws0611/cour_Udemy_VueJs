<template>
<div>
    <ul>
        <li v-for="(film, index) in myArr" v-bind:key="index">
            <div class="card mt-2">
                <div class="card-body ">
                    Titre: {{film.titre}}<br>
                    Date: {{film.date}}
                </div>
            </div>
        </li>
    </ul>
    <div v-on:click="suppri" class="btn btn-danger mt-2">Supprimmer le filme</div>
</div>
</template>

<script>
 export default {
     name: 'ListeApp',
     data(){
         return {
             fruits: ['Mango', 'Pomme', 'Banane', 'Orange']
         }
     },
     methods: {
       
    },
    props: ['myArr']
    
 }
</script>

<style scoped src="./Liste.css">

</style>