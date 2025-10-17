<template>
    <div>
        <p>optional api seminar detail</p>
        <p>injected price:{{ price.quantity }}</p>
        <p>injected special price:{{ specialPrice }}</p>
    </div>   
</template>
    
<script>
    export default{
        inject: ['price', 'specialPrice']
    }
</script>
    
<style>
    
</style>