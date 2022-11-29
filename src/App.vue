<template>
<div>{{greet}} {{name}}</div>
<div v-html="company"></div>
<div v-html="link"></div>
<h2 v-bind:id="headingId">Heading</h2>
<button v-bind:disabled="isDisabled">Bind</button>
<h2 class="underline">UnderLine Text</h2>
<h2 class="underline" v-bind:class="status">Status</h2>
<h2 v-bind:class="isCondition && 'condition'">Apply Condition</h2>
<h2 v-bind:class="isOpen ? 'open': 'closed'">Ticket Status?</h2>
<h2 v-bind:class="['open','condition']">Open and conditioned</h2>
<h2 v-bind:class="[isCondition && 'condition', isOpen ? 'open': 'closed']">Array Conditional Line</h2>
<h2 v-bind:class="{
  condition: isCondition,
  open: !isOpen,
  'isOpen': isOpen
}">Object Conditional Line</h2>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      greet:"Hello",
      name: "Manoz",
      company:'<b>ShikharTech</b>',
      link:`<a href='test' onClick="alert('you are welcome')"> Click Here!</a>`,
      headingId: 'heading',
      isDisabled: false,
      status:'success',
      isCondition:true,
      isOpen:false
    };
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.underline{
  text-decoration: underline;
}

.condition{
  font-style: italic;
}

.open{
  color: green;
}

.closed{
  color: red;
}
</style>
