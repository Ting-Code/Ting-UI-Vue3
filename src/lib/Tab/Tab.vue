<template>
  <div :disabled="disabled">
    <slot />
  </div>
</template>
<script lang="ts">

export default {
  name: "t-tab",
  props: {
    disabled: {
      type: Boolean,
      default: false,
    },
  },
};
</script>

<style lang="scss"></style>
