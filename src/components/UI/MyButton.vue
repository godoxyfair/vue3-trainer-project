<template>
  <button class="btn">
    <slot></slot>
  </button>
</template>

<script>
export default {

}
</script>

<style>
.btn {
  padding: 10px 15px;
  background: none;
  color: cornflowerblue;
  border: 2px solid cornflowerblue;
  font-size: 1em;
}
.btn:hover {
  background-color: cornflowerblue;
  color: aliceblue;
}
</style>
