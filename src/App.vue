<template>
  <div class="main">
    <MyHeader appName="Student Dashboard" />
    <StudentDashboard :students=students />
  </div>
</template>

<script>
import MyHeader from './components/MyHeader.vue'
import StudentDashboard from './components/StudentDashboard.vue'


export default {
  name: 'App',

  components: {
    MyHeader,
    StudentDashboard
  },
  data() {
    return {
      students: []
    }
  },
  methods: {
    async fetchAllStudents() {
      const res = await fetch('https://student-dashboard-node.onrender.com/api');
      const data = await res.json()
      return data.students
    }
  },
  async created() {
    this.students = await this.fetchAllStudents();
  }
}
</script>


<style>
@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@300&display=swap');

* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: 'Montserrat', sans-serif;
}


.main {
  color: black;
  background-color: darkslategray;
}

@media screen and (max-width: 500px) {
  .main{
    width: 100%;
  }
}
</style>
