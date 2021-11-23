<template>
  <div>
    <button @click="getData(color)">Blue</button>
  </div>
</template>

<script>
export default {
  name: "BlueColor",
  data() {
    return {
      color: "blue",
    }
  },
  props:{
    getData : Function
  }
};
</script>

<style>
</style>