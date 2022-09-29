<script setup lang="ts">
import Card from "../components/card.vue";



const unObjet = {
    price: "300 000", 
    name: "Paris",
    adresse: "3 rue Georges",
    bed: 4,
    bathroom: 2,
    Surface:250,
    fav:true,
    image:'src/assets/house4.jpg'

}

</script>

<template>
<<<<<<< HEAD
    <div>
=======
    <div class="flex items-center flex-col">
        <p>Simple</p>
>>>>>>> 50f55225777ecc9888d9a852eacf00bd1f7d5b4a
        <Card></Card>
        <Card v-bind="unObjet"></Card>
    </div>
</template>
