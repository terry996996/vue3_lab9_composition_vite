<template>
    <h3>{{ course }}</h3>
    <h3>Inject:{{ price }}</h3>
</template>
    
<script>
export default{
    props:['courseId', 'courseFullName'], // 接收父傳來的資料
    inject:['price'],
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