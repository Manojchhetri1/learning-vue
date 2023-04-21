<template>
    <div>
        <button v-on:click="update">update</button>
    </div>
</template>

<script>
export default {
    name: 'childParent',
    methods:{
        update(){
            this.$emit('changeText','Text has been changed')
        }
    }
        
}
</script>