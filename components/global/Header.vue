<template>
  <nav class="nav" aria-label="Main Menu">
    <ul class="list-reset nav__list">
      <li class="nav__list-item">
        <nuxt-link class="nav__link" to="/">Home</nuxt-link>
      </li>
      <li class="nav__list-item">
        <nuxt-link class="nav__link" to="/blog">Blog</nuxt-link>
      </li>
      <li class="nav__list-item">
        <nuxt-link class="nav__link" to="/projects">Projects</nuxt-link>
      </li>
    </ul>
  </nav>
</template>

<script>
export default {
  name: 'Header',
}
</script>

<style lang="scss" scoped>
.nav {
  &__list {
    list-style: none;
    display: flex;
    justify-content: flex-end;
  }
  &__link {
    display: block;
    padding: $spacer-md;
    &:last-child {
      padding-right: 0;
    }
  }
}
</style>
