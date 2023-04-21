<template>
    <div class="welcome">
        <h1 class="topic">This is a parent Component.</h1>
        <ChildOne />
        <ChildTwo />
    </div>
</template>

<script>
import ChildOne from './ChildOne.vue';
import ChildTwo from './ChildTwo.vue';

export default {
    name: "WelcomeComponent",
    components: {
        ChildOne,
        ChildTwo,
    }
}
</script>

<style>
.welcome{
    background-color:skyblue ;
    width:auto;
    height: 500px;
}
.topic{
    text-align: center;
}
</style>