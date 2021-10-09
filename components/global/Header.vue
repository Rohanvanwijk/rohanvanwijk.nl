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
  $self: &;
  &__list {
    list-style: none;
    display: flex;
    justify-content: space-between;

    &-item {
      &:first-child {
        #{$self}__link {
          padding-left: 0;
        }
      }
      &:last-child {
        #{$self}__link {
          padding-right: 0;
        }
      }
    }
  }
  &__link {
    display: block;
    padding: $spacer-xl * 2;
  }
}
</style>
