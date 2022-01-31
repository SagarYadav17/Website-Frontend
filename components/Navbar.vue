<template>
  <div class="flex flex-col justify-center px-8">
    <nav
      class="flex items-center justify-between w-full relative max-w-2xl border-gray-700 mx-auto pt-8 pb-8 sm:pb-16 bg-gray-900 bg-opacity-60 text-gray-100"
    >
      <div class="ml-[-0.60rem]">
        <MobileMenu />
        <NavbarItem name="Home" url="/" />
        <NavbarItem name="Blog" url="/blog" />
      </div>
    </nav>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  name: 'Navbar',
})
</script>
