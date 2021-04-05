<template>
  <div class="container-wrapper">
    <div class="container-inner">
      <slot />
    </div>
  </div>
</template>

<style lang="scss" scoped>
.container-wrapper {
  margin: 20px auto;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
}
.container-inner {
  max-width: 750px;
}
</style>
