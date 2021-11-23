<template>
  <div>
    <input type="text" placeholder="Enter Text" v-model="text" />
    <p ref="textStyle" v-if="classShow">{{ text }}</p>
  </div>
  <div>
    <SubmitBtn :getData="submitClassShow" />
    <div v-if="classShow">
      <ZoomIn :size="size" @update-Insize="zoomIn" />
      <ZoomOut :size="size" @update-Outsize="zoomOut" />
      <BlueColor :getData="colorData" />
      <RedColor :getData="colorData" />
    </div>
    <Reset :textProp="text" @update-reset="resetData" />
  </div>
</template>

<script>
import SubmitBtn from "./SubmitBtn.vue";
import ZoomIn from "./ZoomIn.vue";
import ZoomOut from "./ZoomOut.vue";
import BlueColor from "./BlueColor.vue";
import RedColor from "./RedColor.vue";
import Reset from "./Reset.vue";

export default {
  name: "UiComponent",
  data() {
    return {
      classShow: false,
      text: "",
      size: "",
    };
  },
  components: {
    SubmitBtn,
    ZoomIn,
    ZoomOut,
    BlueColor,
    RedColor,
    Reset,
  },
  methods: {
    submitClassShow(par) {
      if (this.text.length !== 0) {
        this.classShow = par;
        if (this.classShow) {
          this.$refs.textStyle.style.fontSize = "20px";
          this.size = this.$refs.textStyle.style.fontSize.slice(0, 2);
          console.log(this.$refs.textStyle.style);
        }
      }
    },
    zoomIn(par) {
      this.$refs.textStyle.style.fontSize = par;
      this.size++;
    },
    zoomOut(par) {
      this.$refs.textStyle.style.fontSize = par;
      this.size--;
    },
    colorData(par) {
      this.$refs.textStyle.style.color = par;
    },
    resetData(par) {
      this.text = par;
      this.classShow = false;
      this.$refs.textStyle.style.removeProperty("color");
      this.$refs.textStyle.style.removeProperty("font-size");
    },
  },
};
</script>

<style>
</style>