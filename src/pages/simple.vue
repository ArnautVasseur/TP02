<script setup lang="ts">
import Card from "../components/card.vue";



const unObjet = {
    price: "300 000", 
    nom: "Paris",
    adresse: "3 rue Georges",
    nbrChambre: 4,
    nbrSDB: 2,
    surface:250,
    fav:true,
    image:'src/assets/house4.jpg'

}

</script>

<template>
    <div class="grid grid-flow-row-dense grid-cols-[repeat(auto-fit,minmax(420px,420px))] justify-around mb-5 mr-56">
        <Card></Card>
        <Card v-bind="unObjet"></Card>
    </div>
</template>
