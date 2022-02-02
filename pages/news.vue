<template>
  <div class="bg-gray-900">
    <main class="flex flex-col justify-center px-8">
      <SideBar />
      <!-- ?SECTION - Child Pages Starts Here -->
      <div class="flex flex-col items-start justify-center w-full m-10">
        <div class="p-4 gap-4 grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-3 select-none">
          <div v-for="news in newsList" v-bind:key="news.id">
            <NewsCard :article="news" />
          </div>
        </div>
      </div>
      <!-- ?SECTION - Child Pages Ends Here -->
    </main>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  name: 'News',
  async asyncData({ $axios }) {
    const { data } = await $axios.get('/news/news/')

    return {
      newsList: data.results,
      nextURL: data.next,
      previousURL: data.previous,
    }
  },
})
</script>
