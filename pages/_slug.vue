<template>
  <div class="bg-gray-900">
    <main class="flex flex-col justify-center px-8 bg-gray-900">
      <SideBar />
      <article class="flex flex-col items-start justify-center w-full max-w-2xl mx-auto mt-5 mb-16">
        <h1 class="mb-4 text-3xl font-bold tracking-tight md:text-5xl text-white">
          {{ title }}
        </h1>
        <div class="flex flex-col items-start justify-between w-full mt-2 md:flex-row md:items-center">
          <div class="flex items-center">
            <Image alt="Sagar Yadav" height="{24}" width="{24}" src="/avatar.jpg" class="rounded-full" />
            <p class="ml-2 text-sm text-gray-300">{{ author }} / {{ publishedAt }}</p>
          </div>
        </div>
        <div class="w-full mt-4 text-white max-w-none">
          {{ content }}
        </div>
      </article>
    </main>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  name: 'BlogPost',
  head() {
    return {
      title: `${this.$data.title} - Sagar Yadav`,
      meta: [
        {
          hid: 'title',
          name: 'title',
          content: `${this.$data.title} - Sagar Yadav`,
        },
        {
          hid: 'description',
          name: 'description',
          content: this.$data.summary,
        },
        {
          hid: 'og:url',
          name: 'og:url',
          content: `${process.env.BASE_URL}/${this.$route.params.slug}`,
        },
        {
          hid: 'og:title',
          name: 'og:title',
          content: `${this.$data.title} - Sagar Yadav`,
        },
        {
          hid: 'og:description',
          name: 'og:description',
          content: `${this.$data.summary}`,
        },
      ],
    }
  },
  async asyncData({ $axios, params }) {
    const { data } = await $axios.get('/blog/posts/' + params.slug)

    return {
      title: data.title,
      content: data.content,
      publishedAt: data.published_date,
      author: data.author,
      summary: data.summary,
    }
  },
})
</script>
