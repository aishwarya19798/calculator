<template>
  <div></div>
</template>

<script>
export default {
  name: "operations",
  methods: {
    arithmeticOperation(a, b, op) {
      a = Number.parseFloat(a)
      b = Number.parseFloat(b)
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
      console.log(res);
    },
  },
  props : [
    "operation"
  ]
};
</script>

<style scoped></style>
