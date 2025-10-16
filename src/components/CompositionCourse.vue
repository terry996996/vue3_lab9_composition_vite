<template>
        <div>
            <p>{{ course }}</p>
            <p>${{ price }}</p>
            <h3>{{ courseDisplayName }}</h3>
            <input type="text" placeholder="請輸入courseId" v-model="courseId">
            <input type="text" placeholder="請輸入courseFullName" v-model="courseFullName">
            

            <!-- &nbsp; -->
            <!-- <button @click="course.duration+=7">increase 1 day</button> -->
            &nbsp;
            <button @click="addCourse">加一天</button>
            <br>
            <p>{{ course2 }}</p>
            <p>${{ price2 }}</p>
            <!-- &nbsp; -->
            <!-- <button @click="course2.duration+=7">increase 1 day</button> -->
            &nbsp;
            <button @click="addCourse2">加一天</button>

        </div>
</template>
    
<script>
    import { reactive, ref, computed } from 'vue'
    export default{
        setup(){
            let price = ref(20000)
            let price2 = ref(25000)
            const courseId = ref('')
            const courseFullName = ref('')

            let course = reactive({
                name: 'POOP',
                duration: 35
            })

            let course2 = ref({
                name: 'AAA',
                duration: 35
            })

            const addCourse = () => {
                course.duration += 7
                price.value += 10000
            }
            const addCourse2 = () => {
                course2.value.duration += 7
                price2.value += 10000
            }

            // const setCourseId = event => courseId.value = event.target.value

            // const setCourseFullName = event => courseFullName.value = event.target.value


            const courseDisplayName = computed(() => {
                console.log('計算屬性被呼叫了')
                return courseId.value + ' ' + courseFullName.value
            })

            return{course, course2, addCourse, addCourse2, price, price2, courseDisplayName, courseId, courseFullName} //, setCourseId, setCourseFullName

        }
    }
</script>
    
<style>
    
</style>