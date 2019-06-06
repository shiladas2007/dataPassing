<template>
  <div>
    <div>
      <h3>user</h3>
      <ul>
        <li><span>Name:</span>{{un}}</li>
        <li><span>LName:</span>{{ln}}</li>
        <li><span>Age:</span>{{age}}</li>
      </ul>
      <h3>Parents</h3>
        <li><span>Father:</span>{{ parents.father }}</li>
        <li><span>Mother:</span>{{ parents.mother }}</li>
      <h3>P</h3>
      <li v-for="(key, value, index) in parents" :key="index">
          <span>{{key}}:</span>{{value}}
      </li>
    </div>
    <button @click="upN">UPN</button>
    <button @click="upLn('ttt')">UPLN</button>
    <div>add fre
      <input type="text" v-model="inp"/>
      <button @click="add">Add Fre</button>
    </div>

  </div>
</template>
<script>
import {bus} from '../../main';
export default {
  data() {
    return {
      inp:''
    }
  },
  props:{
    un:String,ln: String, age:Number, parents:Object, upLn: Function
  },
  methods: {
    upN(){
     this.$emit('upN','new name');
    },
    add(){
      bus.$emit('add',this.inp);
    }

  },
}
</script>
