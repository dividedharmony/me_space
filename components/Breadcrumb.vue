<template>
  <div class="breadcrumb">
    <NuxtLink v-if="to" :to="to">{{ name }}</NuxtLink>
    <a v-else :href="href || '#'">{{ name }}</a>
  </div>
</template>

<script>
export default {
  props: {
    name: {
      type: String,
      required: true,
    },
    to: {
      type: String,
      default: null,
    },
    href: {
      type: String,
      default: null,
    },
  },
}
</script>
