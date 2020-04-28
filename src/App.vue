<template>
  <div id="app">
    <buttons @click="onButtonClick" />
    <outputs :buttonLog="buttonLog" />
    <operations :operation="valuesPassed()" />
  </div>
</template>

<script>
import operations from "./components/Operations";
import buttons from "./components/Buttons";
import outputs from "./components/Outputs";
export default {
  name: "App",
  components: {
    outputs,
    buttons,
    operations,
  },
  data() {
    return {
      buttonLog: [],
    };
  },
  methods: {
    onButtonClick(value) {
      this.buttonLog = [...this.buttonLog, value];
    },
    valuesPassed() {
      // 1. this.buttonLog ko string me krrna
      // 2. check ki kya koi operator h?
      // 2p1. split operator se aur save krralo operator ko
      // 2p2. operations ko split aur operator dedo
      
      // 2n1. kuch nhi krre
      
    },
  },
};
</script>

<style>
* {
  box-sizing: border-box;
}
</style>
