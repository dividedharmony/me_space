<template>
  <Container>
    <div class="above-fold">
      <Headline :size="2">Dungeons &amp; Dragons</Headline>
      <Headline :level="2" :size="4" :decorations="['italic']"
        >Adventures and Suppliments Written by David Harmon</Headline
      >
    </div>
    <div class="below-fold">
      <ul class="articles">
        <li v-for="article in articles" :key="article.href">
          <NuxtLink :to="article.href">
            {{ article.title }}
          </NuxtLink>
        </li>
      </ul>
    </div>
  </Container>
</template>

<script>
export default {
  async asyncData({ $content }) {
    try {
      const articles = await $content('articles/dnd')
        .only(['title', 'description'])
        .fetch()
      articles.forEach((article) => {
        if (article.path) {
          article.href = article.path.replace('articles/', '')
        }
      })
      console.log('ARTICLES', articles)
      return {
        articles,
      }
    } catch (e) {
      // eslint-disable-next-line no-console
      console.error(e)
      return {
        articles: [],
      }
    }
  },
  data() {
    return {
      articles: [],
    }
  },
}
</script>
