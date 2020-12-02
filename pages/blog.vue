<template>
  <div>
    <li v-for="post of posts" :key="post.slug">
      <NuxtLink :to="post.path">{{ post.title }}</NuxtLink>
    </li>
  </div>
</template>

<script>
export default {
   async asyncData({ $content }) {
    const posts = await $content("blog").fetch();

    return {posts};
  },
};
</script>