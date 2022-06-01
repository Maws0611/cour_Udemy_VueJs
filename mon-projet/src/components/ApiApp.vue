<template>
    <div class="api mt-5">
        <h1 class="bg-primary">Appel à l'API</h1>
        <div class="card">
            <div class="card-body">
                <img v-bind:src="urlImage">
            </div>
        </div>
    </div>
</template>

<script>
import axios from 'axios'
    export default {
        name: 'api',
        data(){
            return{
                urlImage: null,
            }
        },
        mounted(){
        axios
        .get('https://api.thecatapi.com/v1/images/search')
        .then(response => {
            this.urlImage=response.data[0].url
            })
    }
    }
</script>

<style scoped>
.api{
    color: white;
}
</style>