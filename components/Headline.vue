<template>
  <h1 :is="`h${level}`" class="headline">
    <slot />
  </h1>
</template>

<script>
export default {
  props: {
    level: {
      type: Number,
      default: 1,
      validator: (value) => {
        return value >= 1 && value <= 6
      },
    },
  },
}
</script>

<style lang="scss" scoped>
.headline {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}
</style>
