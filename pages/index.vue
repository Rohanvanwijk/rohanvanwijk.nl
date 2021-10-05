<template>
  <main>
    <section class="intro block-spacing" :style="{ transform: `rotate(${r}deg)` }">
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

    <section class="mt-8" @mousemove="updateStyle($event)">
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
      r: 0,
    }
  },
  methods: {
    updateStyle(event) {
      if (event.screenX < 450) {
        this.r = event.screenX * -0.01
      } else {
        this.r = event.screenX * 0.01
      }
    },
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
  transition: transform 500ms ease;
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