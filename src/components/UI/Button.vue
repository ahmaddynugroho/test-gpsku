<template>
  <button :class="classes">
    <i :class="faIconTop"></i>
    <p>
      {{ title }}
    </p>
  </button>
</template>

<script>
export default {
  props: {
    title: String,
    faIconLeft: String,
    faIconTop: String,
    classes: String,
  },
}
</script>
