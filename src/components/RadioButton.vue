<template>
  <label class="radio">
    <input type="radio" :label="label" :name="name" />
    <span>{{ label }}</span>
  </label>
</template>
<script>
export default {
  name: "RadioButtons",
  props: {
    label: String,
    name: String
  }
};
</script>script  