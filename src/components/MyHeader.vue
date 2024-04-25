<template>
    <div class="header">
        <h1> {{ appName }} </h1>
    </div>
</template>

<script>
export default {
    name: 'MyHeader',
    props: {
        appName: String,
    }
}
</script>

<style scoped>
.header {
    background-color: burlywood;
    text-align: center;
    padding: 1em 0;
}
</style>