<template>
  <Container>
    <div class="above-fold">
      <Headline :size="2">Software Developer</Headline>
    </div>
    <div class="below-fold">
      <p>
        Working at <a href="https://www.candlescience.com/">CandleScience</a> as
        a Full Stack Developer, I attained mastery of the following technologies
        over the course of 6 years of experience:
      </p>
      <ul>
        <li>
          <a href="https://rubyonrails.org/"> Ruby on Rails </a>
        </li>
        <li>
          <a href="https://www.postgresql.org/">PostgeSQL</a> and
          <a href="https://aws.amazon.com/relational-database/"
            >Relational Databases</a
          >
        </li>
        <li>
          <a href="https://www.w3schools.com/html/html_intro.asp">HTML</a>,
          <a href="https://www.w3schools.com/css/css_intro.asp">CSS</a>, and
          <a
            href="https://developer.mozilla.org/en-US/docs/Learn/JavaScript/First_steps/What_is_JavaScript"
            >JavaScript</a
          >
        </li>
        <li><a href="https://vuejs.org/">Vue.js</a></li>
        <li><a href="https://nuxtjs.org/">NuxtJS</a></li>
        <li><a href="https://jquery.com/">jQuery</a></li>
        <li>
          <a href="https://sass-lang.com/">Sass</a> and
          <a href="https://sass-lang.com/documentation/syntax#scss">SCSS</a>
        </li>
        <li>
          <a href="https://git-scm.com/">Git</a> and
          <a href="https://github.com/features">GitHub</a>
        </li>
        <li>
          <a
            href="https://www.gnu.org/software/bash/manual/html_node/What-is-Bash_003f.html"
            >Bash</a
          >
        </li>
        <li><a href="https://aws.amazon.com/">Amazon Web Services (AWS)</a></li>
        <li>
          <a href="https://www.redhat.com/en/topics/api/what-is-a-rest-api"
            >REST APIs</a
          >
        </li>
        <li><a href="https://www.atlassian.com/agile">Agile Methodology</a></li>
      </ul>

      <hr />

      <Headline :level="2" :size="4" :decorations="['italic']"
        >Programming Projects by David Harmon</Headline
      >
      <p>
        In addition to my professional work, I have a number of personal
        projects that I develop and maintain on my
        <a href="https://github.com/dividedharmony/">personal GitHub account</a
        >.
      </p>
      <ul class="articles">
        <li v-for="article in articles" :key="article.href">
          <NuxtLink :to="article.href || '#'">
            {{ article.title }}
          </NuxtLink>
        </li>
      </ul>
    </div>
  </Container>
</template>

<script>
export default {
  data() {
    return {
      articles: [],
    }
  },
  async fetch() {
    try {
      const articles = await this.$content('articles/programming')
        .only(['title', 'description', 'path', 'rank'])
        .sortBy('rank')
        .fetch()
      articles.forEach((article) => {
        if (article.path) {
          article.href = article.path.replace('articles/', '')
        }
      })
      this.articles = articles
    } catch (e) {
      // eslint-disable-next-line no-console
      console.error(e)
    }
  },
}
</script>
