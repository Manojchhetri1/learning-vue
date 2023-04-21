<template>
    <div class="child1">
        <h1>Child One Component.</h1>
        <h1 v-bind:style="{color:'yellow'}">Child One.</h1>  <!-- style binding -->
        <!-- <h1 v-if="show">class bind.</h1>  -->
         <!-- class binding -->
        <!-- <h1 v-bind:class="[checkDisplay?a:b]">class with array</h1>  -->

    </div>
</template>

<script>
export default {
    name: "ChildOne",
    data(){
        return {
            show: true,
            a:'display',
            b:'hide',
            checkDisplay:false,
        }
    }
}
</script>

<style>
.child1{
    background-color:grey ;
    width: 300px;
    height: 150px;
    margin: 10px;
    padding: 10px;
}
</style>