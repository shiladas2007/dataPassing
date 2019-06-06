<template>
  <div id="app">
    <app-header></app-header>
    <div>main content</div>
    <profile :un="un" :ln="ln" :age="age" :parents="parents"
    @upN="un = $event" :upLn="upLn"
    ></profile>
    <friend></friend>
  <dailyW>
    <p>top text</p>
    <ul slot="sl1"><li>test1</li><li>test2</li><li>test3</li></ul>
    <ul slot="sl2"><li>test6</li><li>test4</li><li>test5</li></ul>
    <p>defalut text</p>
    <div :slot="ot">test ot</div>
  </dailyW>
    <app-footer></app-footer>
  </div>
</template>

<script>
import Footer from './components/footer.vue';
import profile from './components/user/profile.vue';
import friend from './components/user/friend.vue';
import dailyW from './components/user/dailyw.vue';
export default {
  name: 'app',
  data () {
    return {
     un:'shila', ln:'das',age:20, parents:{
       mother:"mot",father:"fat"
     },ot:''
    }
  },
  methods: {
    upLn(value){
      this.ln=value;
  },
  },

    components : {
      'app-footer':Footer,profile, friend, dailyW
    },
    created() {
      setTimeout(()=>{
        this.ot='other';
      },3000)
    },
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
