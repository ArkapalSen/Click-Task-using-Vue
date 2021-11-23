<template>
  <div>
    <button @click='getData(classShow)'>Submit</button>
  </div>
</template>

<script>
export default {
  name : 'SubmitBtn',
  props:{
    getData : Function,
  },
  data(){
    return{
      classShow : true,
      text : '',
    }
  },
  
}
</script>
