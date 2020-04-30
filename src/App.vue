<template>
  <div id="app">
    <buttons
      :buttonLog="buttonLog"
      @click="onButtonClick"
      :operators="operators"
    />
    <outputs :buttonLog="buttonLog" />
    <operations :job="valuesPassed()" />
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
      operators: ["+", "-", "*", "/"],
      buttonLog: [],
    };
  },
  methods: {
    onButtonClick(value) {
      this.buttonLog = [...this.buttonLog, value];
    },
    valuesPassed() {
      // 1. this.buttonLog ko string me krrna
      const input = this.buttonLog.join("");

      // 2. check ki kya koi operator h?
      let operator = null;
      for (const optr of this.operators) {
        if (input.includes(optr)) {
          operator = optr;
          break;
        }
      }

      if (operator) {
        // 2p1. split operator se aur save krralo operator ko
        const operand = input.split(operator);

        // 2p2. operations ko split ki value aur operator dedo
        return [operand, operator]; // [[1,2],+]
      }

      // 2n1. kuch nhi krre
      return null;
    },
  },
};
</script>

<style>

</style>
