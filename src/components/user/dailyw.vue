<template>
  <div>
     <h2>daily work</h2>
     <slot name="sl1"></slot><hr>
     <slot name="sl2"></slot><hr>
     <slot ></slot>
      <slot name="other" >test other</slot>
  </div>
</template>
<script>
export default {
 data(){
   return {
     ar:['test1','test2','test3']
   }
 }
}
</script>

