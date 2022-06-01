<template>
<div>
    <h1 class="bg-success">Notre formulaire</h1>
    <form method="post" action>
        <div class="mb-3">
            <label for="prenom" class="form-label">Ton prénom</label>
            <input v-model="formData.prenom" type="text" class="form-control" id="prenom" placeholder="Asta SÉNE">
        </div>
        <div class="mb-3">
            <label for="text" class="form-label">Ton texte</label>
            <textarea v-model.lazy="formData.texte" class="form-control" id="text" rows="3"></textarea>
        </div>

        <select v-model="formData.selectPays" class="form-select" aria-label="Default select example">
            <option v-bind:key="index" v-for="(pays, index) in formData.listePays">
              {{pays}}
            </option>
        </select>
            
        <div class="form-check">
            <input v-model="formData.checkboxFruit" id="fraise" value="fraise" type="checkbox" class="form-check-input">
            <label for="fraise">Fraise</label>
        </div>
        <div class="form-check">
            <input v-on:input="toggleResultat" v-model="formData.checkboxFruit" id="pomme" value="pomme" type="checkbox" class="form-check-input">
            <label for="pomme">Pomme</label>
        </div>
        <div class="form-check">
            <input v-model="formData.checkboxFruit" id="mangue" value="mangue" type="checkbox" class="form-check-input">
            <label for="mangue">Mangue</label>
        </div>
    </form>
    <button v-on:click="envoyerForm" class="btn btn-primary mt-3">Envoyer les données</button>
    
    <div v-if="formInfo" class="card mt-3">
        <h1 >Résultat</h1>
        <p>Prénom: {{formData.prenom}}</p>
        <p style="white-space:pre">texte: {{formData.texte}}</p>
        <!-- white-space:pre: style permattant d'aller à la ligne en cliquant sur enter -->
        <p>Choix du select: {{formData.selectPays}}</p>
        <p>Résultat checkbox</p>
        <ul>
            <li v-bind:key="index" v-for="(fruit,index) in formData.checkboxFruit">{{fruit}}</li>
        </ul>
    </div>
</div>
</template>

<script>
    export default {
        name: 'formulaireApp',
        data(){
            return{
                formData: 
                    {
                    prenom: '',
                    texte: '',
                    checkboxFruit: [],
                    selectPays: '',
                    listePays: ['Sénégal', 'France', 'Mali', 'Canada']
                    },
                    formInfo: false
               }
        },
        methods: {
            envoyerForm: function(){
                this.formInfo= true
            },
            toggleResultat: function(){
                this.form.formInfo=false
            }
        }
    }
</script>

<style scoped>

</style>


<!-- v-model.lazy  .lazy= c'est un modifier, permet d'ajouter le text aprés terminer d'ecrire
mais cela n'ajoute pas directement le texte en ecrivant -->