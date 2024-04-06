<template>
  <div class="grid">
    <div><slot name="one" /></div>
    <div><slot name="two" /></div>
  </div>
  <div class="statistics">
    <slot name="statistics" />
  </div>
</template>

<script>
export default {
  name: 'BaseLayout'
}
</script>

<style>
.statistics {
  border: 2px solid red;
}
.grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  border: 2px solid red;
}
</style>
