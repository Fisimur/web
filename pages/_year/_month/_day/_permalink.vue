<template>
<article>
    <BlogPost v-slot="{ post, author, error }" :year="$route.params.year" :month="$route.params.month" :day="$route.params.day" :permalink="$route.params.permalink">
      <div v-if="error.code">
        No post found
      </div>
      <article v-else class="max-w-4xl w-full mx-auto">
        <div class="relative">
          <img class="flex-1 h-64 w-full object-cover" :src="blogPostImage(post)" :alt="post.title" />
          <BlogAuthorAvatar
            :author="author"
            class="absolute"
            :style="{ bottom: '1rem', right: '1.8rem' }"
          />
        </div>

        <div class="mt-8">
          <h1 class="mt-2 text-4xl font-medium leading-7">{{ post.title }}</h1>
          <div class="mt-1">
            <span class="text-sm font-medium text-gray-700">{{ post.readingTime }}</span>
            <span>|</span>
            <time class="text-sm font-medium text-gray-700" :datetime="post.createdAt">
              {{ post.createdAt }}
            </time>
          </div>

          <div class="mt-6">
            <nuxt-content :document="post" class="prose sm:prose lg:prose-lg xl:prose-xl" />
          </div>
        </div>
      </article>
    </BlogPost>
  </article>
</template>

<script>
export default {
  name: 'ViewPost',
  methods: {
    blogPostImage(post) {
      if (!post.image) return
      const postImage = post.image
      return postImage.substring(0, 4) === 'http' ? postImage : `/${postImage}`
    },
  }
}
</script>
