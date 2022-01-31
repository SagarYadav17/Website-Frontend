<template>
  <footer class="flex flex-col justify-center items-start max-w-2xl mx-auto w-full mb-8">
    <hr class="w-full border-1 border-gray-800 mb-8" />
    <div class="w-full max-w-2xl grid grid-cols-1 gap-4 pb-16 sm:grid-cols-2">
      <div class="flex flex-col space-y-4">
        <FooterLink name="Home" url="/" />
        <FooterLink name="Blog" url="/blog" />
        <FooterLink name="About" url="/about" />
      </div>
      <div class="flex flex-col space-y-4">
        <FooterLink name="Twitter" url="https://twitter.com/deadwaist" :externalURL="true" />
        <FooterLink name="GitHub" url="https://github.com/sagaryadav17" :externalURL="true" />
        <FooterLink name="LinkedIn" url="https://linkedin.com/in/sagaryadav17" :externalURL="true" />
      </div>
    </div>
  </footer>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  name: 'Footer',
})
</script>
