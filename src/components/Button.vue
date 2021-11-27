<template>
  <button @click="addtext()" :style="{ background: color }" class="btn">
    {{ text }}
  </button>
</template>

<script>
export default {
  name: "Button",
  props: {
    text: String,
    color: String,
  },
  methods: {
    addtext() {
    },
  },
};
</script>
<style scoped>
.btn {
  display: inline-block;
  background: rgb(0, 0, 0);
  color: rgb(0, 0, 0);
  border: double;
  padding: 10px 20px;
  margin: 5px;
  border-radius: 50px;
  cursor: pointer;
  text-decoration: none;
  font-size: 15px;
  font-family: inherit;
}
.btn:focus {
  outline: none;
}
.btn:active {
  transform: scale(0.9);
}
.btn-block {
  display: block;
  width: 100%;
}
</style>