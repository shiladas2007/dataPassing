<template>
  <div id="app">
    <app-header></app-header>
    <div>main content</div>
    <profile :un="un" :ln="ln" :age="age" :parents="parents"
    @upN="un = $event" :upLn="upLn"
    ></profile>
    <friend></friend>

    <app-footer></app-footer>
  </div>
</template>

<script>
import Footer from './components/footer.vue';
import profile from './components/user/profile.vue';
import friend from './components/user/friend.vue';
export default {
  name: 'app',
  data () {
    return {
     un:'shila', ln:'das',age:20, parents:{
       mother:"mot",father:"fat"
     }
    }
  },
  methods: {
    upLn(value){
      this.ln=value;
  },
  },

    components : {
      'app-footer':Footer,profile, friend
    }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
