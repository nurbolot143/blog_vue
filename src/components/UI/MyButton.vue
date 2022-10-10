<template>
  <button><slot></slot></button>
</template>

<script>
export default {
  name: "my-button",
};
</script>

<style scoped>
button {
  padding: 10px 25px;
  border-radius: 5px;
  margin: 5px 0;
  border: 1px solid #008080;
  background: #008080;
  color: #faebd7;
  text-transform: uppercase;
  cursor: pointer;
}
</style>
