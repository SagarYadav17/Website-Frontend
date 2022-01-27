<template>
  <div v-if="externalURL">
    <a
      class="text-gray-500 hover:text-gray-600 transition"
      target="_blank"
      rel="noopener noreferrer"
      :href="url"
    >
      {{ name }}
    </a>
  </div>
  <div v-else>
    <NuxtLink :to="url">
      <a class="text-gray-500 hover:text-gray-600 transition">{{ name }}</a>
    </NuxtLink>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  name: 'FooterLink',
  props: {
    name: {
      type: String,
      required: true,
    },
    url: {
      type: String,
      required: true,
    },
    externalURL: {
      type: Boolean,
      default: false,
    },
  },
})
</script>
