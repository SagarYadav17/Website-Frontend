<template>
  <div class="bg-gray-900 h-screen">
    <main class="flex flex-col justify-center px-8">
      <!-- ?SECTION - Child Pages Starts Here -->
      <div class="flex flex-col items-start justify-center max-w-2xl mx-auto mt-5 mb-16">
        <h1 class="mb-4 text-3xl font-bold tracking-tight md:text-5xl text-white">Blog</h1>
        <p class="my-4 text-gray-400">
          {{ description }}
        </p>
        <div class="relative w-full">
          <input
            aria-label="Search articles"
            type="text"
            placeholder="Search articles"
            class="block w-full px-4 py-2 border rounded-md border-gray-900 focus:ring-blue-500 focus:border-blue-500 bg-gray-800 text-gray-100" @change="console.log()"
          />
          <svg
            class="absolute w-5 h-5 right-3 top-3 text-gray-300"
            xmlns="http://www.w3.org/2000/svg"
            fill="none"
            viewBox="0 0 24 24"
            stroke="currentColor"
          >
            <path strokeLinecap="round" strokeLinejoin="round" strokeWidth="{2}" d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z" />
          </svg>
        </div>

        <h3 class="mt-8 mb-4 text-2xl font-bold tracking-tight md:text-4xl text-white">All Posts</h3>

        <div v-if="posts">
          <div v-for="post in posts" v-bind:key="post.id">
            <NuxtLink :to="post.slug">
              <a class="w-full">
                <div class="w-full mb-8">
                  <div class="flex flex-col justify-between md:flex-row">
                    <h4 class="w-full mb-2 text-lg font-medium md:text-xl text-gray-100">
                      {{ post.title }}
                    </h4>
                    <p class="w-32 mb-4 text-left text-gray-500 md:text-right md:mb-0">
                      {{ post.published_date }}
                    </p>
                  </div>
                  <p class="text-gray-400">
                    {{ post.summary }}
                  </p>
                </div>
              </a>
            </NuxtLink>
          </div>
        </div>
        <p v-else class="mb-4 text-gray-400">No posts found.</p>
      </div>
      <!-- ?SECTION - Child Pages Ends Here -->
    </main>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import axios from 'axios'

export default Vue.extend({
  name: 'Blog',
  head() {
    return {
      title: 'Blog | Sagar Yadav',
      meta: [
        {
          hid: 'title',
          name: 'title',
          content: 'Blog | Sagar Yadav',
        },
        {
          hid: 'description',
          name: 'description',
          content: this.$data.description,
        },
        {
          hid: 'og:url',
          name: 'og:url',
          content: `${process.env.BASE_URL}`,
        },
        {
          hid: 'og:title',
          name: 'og:title',
          content: 'Blog | Sagar Yadav',
        },
        {
          hid: 'og:description',
          name: 'og:description',
          content: this.$data.description,
        },
      ],
    }
  },

  async asyncData({ $axios }) {
    const { data } = await $axios.get('/blog/posts')
    return {
      posts: data.results,
      description: `Well, Hello There. Thanks for checking my blog. In total, I've written ${data.count} articles on my blog. Use the search below to filter by title.`,
    }
  },

  methods: {
    searchPosts(query: string) {
      this.$axios.get('/blog/posts?q=' + query).then((response) => {
        return { posts: response.data.results }
      })
    },
  },
})
</script>
