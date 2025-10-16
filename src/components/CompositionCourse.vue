<template>
        <div>
            {{ course }}
            &nbsp;
            <button @click="course.duration+=7">increase 1 day</button>
            &nbsp;
            <button @click="addCourse">加一天</button>
            <br>
            {{ course2 }}
            &nbsp;
            <button @click="course2.duration+=7">increase 1 day</button>
            &nbsp;
            <button @click="addCourse2">加一天</button>

        </div>
</template>
    
<script>
    import { reactive, ref } from 'vue'
    export default{
        setup(){
            let course = reactive({
                name: 'POOP',
                duration: 35
            })

            let course2 = ref({
                name: 'AAA',
                duration: 35
            })

            const addCourse = () => course.duration+=7
            const addCourse2 = () => course2.value.duration+=7

            return{course, course2, addCourse, addCourse2}

        }
    }
</script>
    
<style>
    
</style>