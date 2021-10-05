<template>
  <main>
    <section class="intro block-spacing">
      <h1 class="title text-center">{{ homeData.title }}</h1>
      <div class="skills">
        <div class="intro__image">
          <img :src="homeData.profileImage" alt="Profile image of Rohan" />
        </div>
        <ul class="intro__list">
          <li v-for="(skill, index) in homeData.skills" :key="index">{{ skill }}</li>
        </ul>
      </div>
    </section>

    <section class="mt-8">
      <h2 class="text-primary-600 dark:text-primary-400 max-w-5xl mx-auto">Recent blog post</h2>
      <posts post-type="blog" :amount="3" />
    </section>
  </main>
</template>
<script>
import homeData from '@/content/site/home.json'
export default {
  name: 'Index',
  data() {
    return {
      homeData,
    }
  },
}
</script>
<style lang="scss" scoped>
.intro {
  display: flex;
  flex-direction: column;
  align-items: center;
  border: 1px dashed $color-tertiary;
  padding: $spacer-md;
  &__list {
    list-style-type: '\1F525';
  }
  &__image {
    $size: 8rem;
    img {
      width: $size;
      height: $size;
      object-fit: cover;
      border-radius: 50%;
    }
  }
}
.skills {
  display: flex;
  align-items: center;
}
</style>