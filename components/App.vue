<template>
<div class="app">
    <p>{{ app }}</p>
</div>
</template>

<script>
export default {
  name: "App",
  props: ["app", "id"],
};
</script>

<style>
.app {
  padding: 1rem;
  border: 1px dotted #ccc;
  margin: 1rem 0;
}
</style>