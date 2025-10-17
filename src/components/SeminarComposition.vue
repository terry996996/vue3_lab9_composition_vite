<template>
    <div>
        <p>composition api seminar detail</p>
        <p>injected price:{{ price.quantity }}</p>
        <p>injected special price:{{ specialPrice }}</p>
    </div>
</template>

<script>
import { inject } from 'vue'
export default {
    setup() {
        const price = inject("price")
        const specialPrice = inject("specialPrice")
        return { price, specialPrice }
    }
}
</script>

<style lang="scss" scoped></style>