<template>
  <div class="container-wrapper">
    <div class="container-inner">
      <slot />
    </div>
  </div>
</template>

<style lang="scss" scoped>
.container-wrapper {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
}
.container-inner {
  max-width: 750px;
}
</style>
