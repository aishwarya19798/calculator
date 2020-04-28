<template>
  <div>
    <button
      v-bind:key="n"
      v-for="(num, n) in numbers"
      @click="$emit('click', num)"
    >
      {{ num }}
    </button>
    <button
      v-bind:key="o"
      v-for="(opr, o) in operators"
      @click="$emit('click', opr)"
    >
      {{ opr }}
    </button>
  </div>
</template>

<script>
export default {
  name: "buttons",
  props: ["operators"],
  data() {
    return {
      numbers: [1, 2, 3, 4, 5, 6, 7, 8, 9],
    };
  },
};
</script>

<style scoped>
div {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  grid-column-gap: 3px;
  grid-row-gap: 3px;
  /* justify-content: center;
  align-content: center;
  align-items: center; */
}
div button {
  border: 1px solid gray;
  border-radius: 1px;
  height: 50px;
  width: 50px;
  /* display: grid;
  justify-content: center;
  align-content: center;
  align-items: center; */
}
</style>
