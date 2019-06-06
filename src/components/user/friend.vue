<template>
  <div>
    <h2>friend</h2>
    <li v-for="(fr, index) in friends" :key="index">
          <span>{{fr}}</span>
      </li>
  </div>
</template>
<script>
import {bus} from '../../main';
export default {
  data(){
    return {
      friends:['fr1','fr2']
    }
  },
  created() {
    bus.$on('add',(value)=>{
      this.friends.push(value);
    })
  },
}
</script>

