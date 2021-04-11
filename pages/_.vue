<template>
  <Container>
    <div v-if="!!article" class="loaded-article">
      <Breadcrumb v-if="parent" :name="parent.name" :to="parent.href" />
      <div class="above-fold">
        <Headline :size="2">{{ article.title }}</Headline>
      </div>
      <div class="below-fold">
        <a
          v-if="article.external_url && article.image"
          :href="article.external_url"
        >
          <img
            :src="article.image"
            :alt="article.title"
            class="article-image"
          />
        </a>
        <img
          v-else-if="article.image"
          :src="article.image"
          :alt="article.title"
          class="article-image"
        />
        <nuxt-content class="article-body" :document="article" />
      </div>
      <div class="article-footer">
        <a v-if="article.external_url" :href="article.external_url"> </a>
        <Breadcrumb
          v-if="article.external_url && article.external_location"
          :name="externalLinkText"
          :href="article.external_url"
        />
      </div>
    </div>
  </Container>
</template>

<script>
export default {
  data() {
    return {
      article: null,
      parent: null,
    }
  },
  async fetch() {
    try {
      const article = await this.$content('articles', this.$route.path).fetch()
      this.article = article
      this.parent = article.parent
    } catch (e) {
      // eslint-disable-next-line no-console
      console.error(e)
    }
  },
  computed: {
    externalLinkText() {
      return `See on ${this.article.external_location}`
    },
  },
}
</script>

<style lang="scss" scoped>
.article-image {
  display: inline-block;
  width: 100px;
  margin: 10px 10px 10px 0;
}
</style>
