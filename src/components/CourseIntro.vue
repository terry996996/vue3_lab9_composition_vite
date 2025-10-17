<template>
    <h3>{{ course }}</h3>
    <h3>{{ price }}</h3>
</template>
    
<script>
export default{
    props:['price', 'courseId', 'courseFullName'], // 接收父傳來的資料
    computed:{
        course(){
            if(!this.courseFullName){
                return `[${this.courseId}]`
            }
            return `[${this.courseId}]${this.courseFullName}`
        }
    }
}
    
</script>
    
<style>
    
</style>