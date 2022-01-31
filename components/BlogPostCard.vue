<template>
  <NuxtLink to="/blog">
    <a class="transform hover:scale-[1.01] transition-all rounded-xl w-full md:w-1/3 bg-gradient-to-r p-1 from-[#D8B4FE] to-[#818CF8]">
      <div class="flex flex-col justify-between h-full bg-gray-900 rounded-lg p-4">
        <div class="flex flex-col md:flex-row justify-between">
          <h4 class="text-lg md:text-lg font-medium mb-6 sm:mb-10 w-full text-gray-100 tracking-tight">
            {{ title }}
          </h4>
        </div>
      </div>
    </a>
  </NuxtLink>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  name: 'BlogPostCard',
  props: {
    title: {
      type: String,
      required: true,
    },
    slug: {
      type: String,
      required: true,
    },
  },
})
</script>
