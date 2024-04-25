<template>
    <div class="student-card">
            <img :src="student.image" class="image" alt="" width="150" height="150">
        <div class="student-details">
            <h4 class="name">{{ student.name }}</h4>
                <p class="department">{{ student.department }}</p>
                <p class="email">{{ student.email }}</p>
                <p class="phone">{{ student.phone_number }}</p>
        </div>
    </div>
</template>

<script>

export default {
    name: 'StudentDetail',
    props: {
        student: Object
    }
}
</script>

<style scoped>

.student-card {
    display: flex;
    justify-content: space-evenly;
    padding: 0.5em 1em;
    background-color: darkcyan;
    color: white;
    border: 1px solid white;
}
.name {
    margin-top: 15px;
}

.image {
    border-radius: 50%;
}

.department, .email,.phone {
    margin: 15px 0;
}
name {
    margin: 2px;
    font-size: 18px;
    font-weight: bolder;
}

@media screen and (max-width: 500px){
    .student-card {
        flex-direction: column;
        text-align: center;
        align-items: center;
    }
}

</style>