<template>
  <div class="bg-gray-900">
    <Navbar />
    <main class="flex flex-col justify-center px-8 bg-gray-900">
      <article
        class="flex flex-col items-start justify-center w-full max-w-2xl mx-auto mb-16"
      >
        <h1
          class="mb-4 text-3xl font-bold tracking-tight md:text-5xl text-white"
        >
          {{ title }}
        </h1>
        <div
          class="flex flex-col items-start justify-between w-full mt-2 md:flex-row md:items-center"
        >
          <div class="flex items-center">
            <Image
              alt="Sagar Yadav"
              height="{24}"
              width="{24}"
              src="/avatar.jpg"
              class="rounded-full"
            />
            <p class="ml-2 text-sm text-gray-300">
              {{ writer }} / {{ publishedAt }}
            </p>
          </div>
        </div>
        <div class="w-full mt-4 text-white max-w-none">
          {{ content }}
        </div>
      </article>

      <Footer />
    </main>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  name: 'BlogPost',
})
</script>
