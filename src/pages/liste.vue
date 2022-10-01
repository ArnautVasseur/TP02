<script setup lang="ts">
    import Card from "../components/card.vue";
    import Maisons from "@/assets/Maisons.json";
    </script>
        
        
    <template>
            <div class="grid grid-flow-row-dense grid-cols-[repeat(auto-fit,minmax(420px,420px))] justify-around py-8 mr-40">
                <Card v-for="maison in Maisons" :key="maison" v-bind="maison"></Card>
            </div>
    </template>