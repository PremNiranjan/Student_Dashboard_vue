<template>
    <div class="student-list">
        <div class="students" v-for="student of students" :key="student.id">
            <StudentDetail :student=student />
            </div>
    </div>
</template>
<script>
import StudentDetail from './StudentDetail.vue'

export default {
    name: 'StudentDashboard',
    props: {
        students: Array
    },
    components: {
        StudentDetail
    }

}
</script>
<style scoped>
.student-list {
    display: flex;
    flex-wrap: wrap;
    width: 80%;
    margin: auto;
}

.students {
    width: 48%;
    margin: 1em 0.5em;
}

@media screen and (max-width: 920px){
    .student-list {
        flex-direction: column;
    }
    .students {
        width: 80%;
        margin: 1em auto;
    }
}
@media screen and (max-width: 576px){
    .students{
        width: 100%;
    }
}
</style>
