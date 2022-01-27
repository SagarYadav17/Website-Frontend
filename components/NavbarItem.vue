<template>
  <NuxtLink :to="url">
    <a
      class="hidden md:inline-block p-1 sm:px-3 sm:py-2 rounded-lg hover:bg-gray-800 transition-all"
    >
      <span class="capsize">{{ name }}</span>
    </a>
  </NuxtLink>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  name: 'NavbarItem',
  props: {
    name: {
      type: String,
      required: true,
    },
    url: {
      type: String,
      required: true,
    },
  },
})
</script>
