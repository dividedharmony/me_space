---
title: me_space
description: 'A Vue.js web application that utilizes the NuxtJS framework.'
rank: 1
parent:
  name: "Programming"
  href: "/programming"
---

This [Vue.js](https://vuejs.org/) web application is the code that powers the [davidharmon.io](https://www.davidharmon.io) website. Using the [NuxtJS](https://nuxtjs.org/) framework, `me_space` has the look and feel of a Single-Page Application but is statically generated, improving SEO and performance.

### Ruby on Rails vs. Vue on Nuxt

As davidharmon.io is a personal site, it does not need a database. Therefore, it makes more sense for `me_space` to use an all-frontend framework like NuxtJS rather than a server-heavy framework like Rails.

Content on davidharmon.io is managed through the git-based, headless CMS [Nuxt Content](https://content.nuxtjs.org/) that is committed directly to the `me_space` repository.

Davidharmon.io is hosted on [Netlify](https://www.netlify.com/), which allows `me_space` to be deployed into a competely serverless environment.
