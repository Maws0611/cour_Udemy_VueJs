<template>
    <div class="block-modale" v-if="revel">
        <div class="overlay" v-on:click="toggleModal"></div>
        <div class="modale card">
            <div class="btn-modale btn btn-danger" v-on:click="toggleModal">X</div>
            <h1>le contenue de la modal</h1>
        </div>
    </div>
</template>

<script>
export default {
    name: 'ModaleApp',
    props: ['revel', 'toggleModal']
    }
</script>

<style scoped>
.block-modale{
position: fixed;
top: 0;
bottom: 0;
left: 0;
right: 0;
width: 100%;
height: 100%;
display:flex;
justify-content: center;
align-items: center;
}
.overlay {
    background: rgba(0, 0, 0, 0.5 );
    position: fixed;
    top: 0;
    left: 0;
    bottom: 0;
    right: 0;
}
.modale{
    background: #f1f1f1;
    color: #0333;
    padding:50px;
    position: fixed;
}
.btn-modale{
    position: fixed;
    top:10px;
    right:10px;
}
</style>