<template>
  <div class="breadcrumb">
    <NuxtLink :to="href">{{ name }}</NuxtLink>
  </div>
</template>

<script>
export default {
  props: {
    name: {
      type: String,
      required: true,
    },
    href: {
      type: String,
      required: true,
    },
  },
}
</script>
