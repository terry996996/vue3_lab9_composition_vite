<template>
        <div>
            <h3>{{ courseDisplayName }}</h3>
            <CourseIntro :courseId="courseId" :courseFullName="courseFullName"/>
            <CourseIntroComposition :courseId="courseId" :courseFullName="courseFullName"/>
            <p>{{ course }}</p>
            <p>${{ price }}</p>
            <input type="text" placeholder="請輸入courseId" v-model="courseId">
            <input type="text" placeholder="請輸入courseFullName" ref="courseFullNameInput"><!-- 標籤的ref屬性，用在HTML標籤上，獲取的是DOM元素-->
            <button @click="setCourseFullName">set course full name</button>

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
    import { reactive, ref, computed, watch, provide } from 'vue'
    import CourseIntro from './CourseIntro.vue';
    import CourseIntroComposition from './CourseIntroComposition.vue';
    export default{
        components:{CourseIntro, CourseIntroComposition},
        setup(){
            let price = ref(20000)
            let price2 = ref(25000)
            const courseId = ref('')
            const courseFullName = ref('')
            const courseFullNameInput = ref()
            
            provide("price", price) // 跨代傳送

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

            const setCourseFullName = () => {
            console.log("courseFullNameInput=",courseFullNameInput)
            console.log("courseFullNameInput.value=",courseFullNameInput.value) // 獲取DOM元素
            courseFullName.value = courseFullNameInput.value.value
        }

            // const setCourseId = event => courseId.value = event.target.value

            // const setCourseFullName = event => courseFullName.value = event.target.value


            const courseDisplayName = computed(() => {
                console.log('計算屬性被呼叫了')
                return courseId.value + ' ' + courseFullName.value
            })

            // watch(price, (n,o) => {
            //     console.log('price變化了', n, o)
            // })

            // watch(price2, (n,o) => {
            //     console.log('price2變化了', n, o)
            // })

            watch([price, price2], (n, o) => {
                if(n[0] !== o[0]){
                    console.log('price變化了', n[0], o[0])
                }
                
                if(n[1] !== o[1]){
                    console.log('price1變化了', n[1], o[1])
                }
            })

            return{course, course2, addCourse, addCourse2, price, price2, courseDisplayName, courseId, courseFullName, courseFullNameInput, setCourseFullName} //, setCourseId, setCourseFullName

        }
    }
</script>
    
<style>
    
</style>