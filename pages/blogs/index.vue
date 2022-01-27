<template>
  <div class="bg-gray-900">
    <Navbar />
    <main class="flex flex-col justify-center px-8 bg-gray-900">
      <!-- ?SECTION - Child Pages Starts Here -->
      <div
        class="flex flex-col items-start justify-center max-w-2xl mx-auto mb-16"
      >
        <h1
          class="mb-4 text-3xl font-bold tracking-tight md:text-5xl text-white"
        >
          Blog
        </h1>
        <p class="mb-4 text-gray-400">
          I've been writing online since 2014, mostly about web development and
          tech careers. In total, I've written 0 articles on my blog. Use the
          search below to filter by title.
        </p>
        <div class="relative w-full mb-4">
          <input
            aria-label="Search articles"
            type="text"
            placeholder="Search articles"
            class="block w-full px-4 py-2 border rounded-md border-gray-900 focus:ring-blue-500 focus:border-blue-500 bg-gray-800 text-gray-100"
          />
          <svg
            class="absolute w-5 h-5 right-3 top-3 text-gray-300"
            xmlns="http://www.w3.org/2000/svg"
            fill="none"
            viewBox="0 0 24 24"
            stroke="currentColor"
          >
            <path
              strokeLinecap="round"
              strokeLinejoin="round"
              strokeWidth="{2}"
              d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z"
            />
          </svg>
        </div>

        <h3
          class="mt-8 mb-4 text-2xl font-bold tracking-tight md:text-4xl text-white"
        >
          All Posts
        </h3>
        <p class="mb-4 text-gray-400">No posts found.</p>
        <NuxtLink :to="'blogs/' + 'slug'">
          <a class="w-full">
            <div class="w-full mb-8">
              <div class="flex flex-col justify-between md:flex-row">
                <h4
                  class="w-full mb-2 text-lg font-medium md:text-xl text-gray-100"
                >
                  Some Title
                </h4>
                <p
                  class="w-32 mb-4 text-left text-gray-500 md:text-right md:mb-0"
                >
                  14th May 2020
                </p>
              </div>
              <p class="text-gray-400">
                Lorem ipsum dolor sit amet consectetur adipisicing elit. Non,
                hic veniam? Ut amet mollitia, dolorem maxime libero tempora
                aliquam commodi quae recusandae voluptatibus et excepturi in, a
                odio quos esse!
              </p>
            </div>
          </a>
        </NuxtLink>
      </div>
      <!-- ?SECTION - Child Pages Ends Here -->
      <Footer />
    </main>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  name: 'Blog',
  head() {
    return {
      title: 'Blog | Sagar Yadav',
    }
  },
})
</script>
