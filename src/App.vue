<template>
<div>{{greet}} {{name}}</div> <!--printing hello world-->
<div v-html="company"></div> <!--making text bold-->
<div v-html="link"></div> <!--alert pop up-->
<h2 v-bind:id="headingId">Heading</h2> <!--binding html-->
<button v-bind:disabled="isDisabled">Bind</button><!--binding to attribute-->
<h2 class="underline">UnderLine Text</h2><!--binding style -->
<h2 class="underline" v-bind:class="status">Status</h2><!--style and class binding -->
<h2 v-bind:class="isCondition && 'condition'">Apply Condition</h2><!--binding style applying condition-->
<h2 v-bind:class="isOpen ? 'open': 'closed'">Ticket Status?</h2>
<h2 v-bind:class="['open','condition']">Open and conditioned</h2>
<h2 v-bind:class="[isCondition && 'condition', isOpen ? 'open': 'closed']">Array Conditional Line</h2>
<h2 v-bind:class="{
  condition: isCondition,
  open: !isOpen,
  'isOpen': isOpen
}">Object Conditional Line</h2><!--bind shorthand-->

<h2 v-if="(num === 0)">The number is zero</h2><!--applying if else statement-->
<h2 v-else-if="(num < 0)">The number is negative</h2>
<h2 v-else-if="(num > 0)">The number is positive</h2>
<h2 v-else>Not a number</h2>

<h2 v-show="showElement">Using v-show</h2><!--rendering conditional element v-show derective-->
<h2 v-if="showElement">Using v-if</h2>

<h2 v-for="(name, index) in names" :key="name">{{index}} {{ name }}</h2><!--applying for loop -->
<h2 v-for="name in fullnames" :key="name.first">{{name.first}} {{ name.last }}</h2>

<div v-for="actor in actors" :key="actor.name"><!--rendering array in array-->
  <h2>{{actor.name}}</h2>
  <h3 v-for="movie in actor.movies" :key="movie">{{movie}}</h3>
</div>

<h2 v-for="(value, key, index) in myinfo" :key="value">{{index}} {{key}} {{value}}</h2><!--rendering in term of key value and index-->
<template v-for="name in names" :key="name">
  <h2>{{name}}</h2>
  <hr />

</template>
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
      isOpen:false,
      num: 3,
      showElement:false,
      names:['vue1','vue2','vue3'],
      fullnames:[
        {first:'manoz', last:'chhetri'},
        {first:'bijay', last:'limbu'},
        {first:'frank', last:'shrestha'}
      ],
      actors:[
        {
          name: 'Rajesh Hamal',
          movies: ['movie1','movie2'],
        },
        {
          name: 'Mr. Bachhan',
          movies: ['sholey', 'kholey'],
        }
      ],
      myinfo:{
        name:'Manoz',
        company:'Shikhartech',
        location:'balkumari'
      }
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
