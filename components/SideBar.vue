<template>
  <div class="flex">
    <div class="fixed top-0 left-0 h-screen w-16 m-1 flex flex-col bg-gray-900 text-white shadow-lg">
      <div v-for="item in sideBarItems" v-bind:key="item">
        <a
          :href="item.url"
          class="group relative flex items-center justify-center h-12 w-12 mt-2 mb-2 mx-auto shadow-lg bg-gray-800 text-green-500 hover:bg-green-600 hover:text-white rounded-3xl hover:rounded-xl transition-all duration-300 ease-linear"
        >
          {{ item.icon }}
          <span
            class="absolute w-auto p-2 m-2 min-w-max left-14 rounded-md shadow-md text-white bg-gray-900 text-xs font-bold transition-all duration-100 scale-0 origin-left group-hover:scale-100"
            >{{ item.name }}</span
          >
        </a>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  name: 'SideBar',
  data() {
    return {
      sideBarItems: [
        { icon: 'H', name: 'Home', url: '/' },
        { icon: 'N', name: 'News', url: '/news' },
      ],
    }
  },
})
</script>
