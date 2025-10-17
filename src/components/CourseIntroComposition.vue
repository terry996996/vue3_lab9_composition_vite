<template>
    <h3>{{ course }}</h3>
    <h3>{{ price }}</h3>
</template>
    
<script>
import {computed} from 'vue'
export default{
    props:['price', 'courseId', 'courseFullName'], // 接收父傳來的資料
    setup(props){


    const course = computed(() => {
        if(!props.courseFullName){
                return `[${props.courseId}]`
            }
            return `[${props.courseId}]${props.courseFullName}` // props裡面接收的資料直接用props.去拿就可以了，不用再.value
        }
    )

    return{course}
    
    
    }
}
    
</script>
    
<style>
    
</style>