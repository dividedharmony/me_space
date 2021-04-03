<template>
  <b-navbar toggleable="lg" type="dark" variant="info">
    <b-navbar-brand>
      <NuxtLink to="/" class="brand-link"> davidharmon.io </NuxtLink>
    </b-navbar-brand>

    <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

    <b-collapse id="nav-collapse" is-nav>
      <!-- Right aligned nav items -->
      <b-navbar-nav class="ml-auto">
        <b-nav-item href="#">Software Developer</b-nav-item>
        <b-nav-item href="#">D&amp;D Writer</b-nav-item>
      </b-navbar-nav>
    </b-collapse>
  </b-navbar>
</template>

<style lang="scss" scoped>
.brand-link {
  color: white;

  &:hover {
    text-decoration: none;
  }
}
</style>
