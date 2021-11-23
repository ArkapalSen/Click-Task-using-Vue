<template>
  <div>
    <button @click="reset">Reset</button>
  </div>
</template>

<script>
export default {
  name: "Reset",
  props: {
    textProp: String,
  },
  methods: {
    reset() {
      let resetText = this.textProp;
      resetText = "";
      this.$emit("update-reset", resetText);
    },
  },
};
</script>

<style>
</style>