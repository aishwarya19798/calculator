<template>
  <div>
    Result :
    <div v-if="job">
      {{ arithmeticOperation(job[0][0], job[0][1], job[1]) }}
    </div>
  </div>
</template>

<script>
export default {
  name: "operations",
  methods: {
    arithmeticOperation(a, b, op) {
      a = Number.parseFloat(a);
      b = Number.parseFloat(b) || 0;
      let res = undefined;
      switch (op) {
        case "+":
          res = a + b;
          break;
        case "-":
          res = a - b;
          break;
        case "/":
          res = a / b;
          break;
        case "*":
          res = a * b;
          break;
      }
      return res;
    },
  },
  props: ["job"],
};
</script>

<style scoped></style>
