<template>
  <b-navbar fixed="top" toggleable="lg" type="dark" variant="info">
    <b-navbar-brand>
      <NuxtLink to="/" class="undecorated"> davidharmon.io </NuxtLink>
    </b-navbar-brand>

    <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

    <b-collapse id="nav-collapse" is-nav>
      <!-- Right aligned nav items -->
      <b-navbar-nav class="ml-auto">
        <b-nav-item>
          <NuxtLink to="/programming" class="undecorated">
            Software Developer
          </NuxtLink>
        </b-nav-item>
        <b-nav-item>
          <NuxtLink to="/dnd" class="undecorated"> D&amp;D Writer </NuxtLink>
        </b-nav-item>
      </b-navbar-nav>
    </b-collapse>
  </b-navbar>
</template>

<style lang="scss" scoped>
.undecorated {
  color: white;

  &:hover {
    text-decoration: none;
  }
}
</style>
