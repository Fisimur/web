<template>
  <BlogPostList v-slot="{ posts }">
    <div class="grid gap-12 lg:grid-cols-2">
      <BlogPostListItem v-for="post in posts" :key="post.path" :post="post" />
    </div>
  </BlogPostList>
</template>

<script>
export default {
  name: 'Index',
}
</script>
