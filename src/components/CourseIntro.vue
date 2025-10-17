<template>
    <h3>{{ course }}</h3>
    <h3>{{ price }}</h3>
</template>
    
<script>
export default{
    props:['course', 'price'], // 接收父傳來的資料
    setup(){
        return{}
    }
}
    
</script>
    
<style>
    
</style>