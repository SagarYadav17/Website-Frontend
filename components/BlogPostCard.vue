<template>
  <NuxtLink :to="slug">
    <a class="rounded-xl w-full md:w-1/3">
      <div class="flex flex-col justify-between h-full bg-gray-900 rounded-lg p-4">
        <div class="flex flex-col md:flex-row justify-between">
          <h4 class="text-lg md:text-lg font-medium mb-2 sm:mb-10 w-full text-gray-100 tracking-tight">
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
