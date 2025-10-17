<template>
    <h3>{{ course }}</h3>
    <h3>Inject:{{ price }}</h3>
</template>
    
<script>
import {computed, inject} from 'vue'
export default{
    props:['courseId', 'courseFullName'], // 接收父傳來的資料
    setup(props){

    const price = inject("price")

    const course = computed(() => {
        if(!props.courseFullName){
                return `[${props.courseId}]`
            }
            return `[${props.courseId}]${props.courseFullName}` // props裡面接收的資料直接用props.去拿就可以了，不用再.value
        }
    )

    return{course, price}
    
    
    }
}
    
</script>
    
<style>
    
</style>