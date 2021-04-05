<template>
  <Container>
    <div v-if="!!article" class="loaded-article">
      <Breadcrumb v-if="parent" :name="parent.name" :href="parent.href" />
      <div class="above-fold">
        <Headline :size="2">{{ article.title }}</Headline>
      </div>
      <div class="below-fold">
        <nuxt-content :document="article" />
      </div>
    </div>
  </Container>
</template>

<script>
export default {
  async asyncData({ $content, params, error }) {
    try {
      const article = await $content(`articles/${params.pathMatch}`).fetch()
      return {
        article,
        parent: article.parent,
      }
    } catch (e) {
      // eslint-disable-next-line no-console
      console.error(e)
      error({ statusCode: 404, message: 'Page not found!' })
    }
  },
  data() {
    return {
      article: null,
      parent: null,
    }
  },
}
</script>
