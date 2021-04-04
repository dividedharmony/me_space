<template>
  <aside class="profile">
    <img
      class="profile-image"
      src="~/assets/images/me.jpeg"
      alt="David Harmon"
    />
    <ul class="social-media-links">
      <li class="social-media">
        Github:
        <a href="https://github.com/dividedharmony/" class="link"
          >@dividedharmony</a
        >
      </li>
      <li class="social-media">
        Twitter:
        <a href="https://twitter.com/dharmon202" class="link">@dharmon202</a>
      </li>
      <li class="social-media">
        Facebook:
        <a href="https://www.facebook.com/david.the.harmon" class="link"
          >@David Harmon</a
        >
      </li>
      <li class="social-media">
        LinkedIn:
        <a href="https://www.linkedin.com/in/harmond/" class="link"
          >/in/harmond</a
        >
      </li>
    </ul>
  </aside>
</template>

<style lang="scss" scoped>
.profile {
  margin: 10px;
  position: fixed;
  top: 60px;
}

.profile-image {
  height: 200px;
  width: 200px;
}

.social-media-links {
  list-style-type: none;
  padding: 0;
  margin: 0;
}

.link {
  color: rgb(51, 51, 51);

  &:hover {
    color: rgb(63, 63, 63);
  }
}
</style>
