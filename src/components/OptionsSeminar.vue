<template>
    <div>
        <h1>options API seminar</h1>
        <h3>price={{ price.quantity }}</h3>
        <h3>special price={{ specialPrice }}</h3>
        <button @click="addPrice">add price</button>
        <button @click="addSpecialPrice">add special price</button>
        <seminar-intro></seminar-intro>
        <seminar-composition></seminar-composition>
    </div>
</template>

<script>
import SeminarIntro from './SeminarIntro.vue';
import SeminarComposition from './SeminarComposition.vue';
import { computed } from 'vue'
export default {
    components: { SeminarIntro, SeminarComposition },
    provide() {
        return {
            price: this.price,
            specialPrice: computed(() => this.specialPrice)
        }
    },
    data() {
        return {
            price: { quantity: 3500 },
            specialPrice: 2500
        }
    },
    methods: {
        addPrice() {
            this.price.quantity += 1000
        },
        addSpecialPrice() {
            this.specialPrice += 800
        }
    }
}
</script>

<style lang="scss" scoped></style>