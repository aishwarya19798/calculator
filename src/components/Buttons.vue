<template>
  <div>
    <button
      v-bind:key="n"
      v-for="(num, n) in numbers"
      @click="$emit('click', num)"
    >
      {{ num }}
    </button>
    <div>
      <button
        v-bind:key="o"
        v-for="(opr, o) in operators"
        @click="operatorClicked(opr)"
      >
        {{ opr }}
      </button>
    </div>
  </div>
</template>

<script>
export default {
  name: "buttons",
  props: ["operators", "buttonLog"],
  data() {
    return {
      numbers: [1, 2, 3, 4, 5, 6, 7, 8, 9],
      isOperatorClicked: false,
    };
  },
  methods: {
    operatorClicked(value) {
      if (!this.isOperatorClicked && this.buttonLog.length > 0) {
        this.isOperatorClicked = true;
        this.$emit("click", value);
      }
    },
  },
};
</script>

<style scoped>

</style>
