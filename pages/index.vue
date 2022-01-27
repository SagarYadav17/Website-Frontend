<template>
  <div class="bg-gray-900">
    <Navbar />
    <main class="flex flex-col justify-center px-8 bg-gray-900">
      <div
        class="flex flex-col justify-center items-start max-w-2xl border-gray-700 mx-auto pb-16"
      >
        <div class="flex flex-col-reverse sm:flex-row items-start">
          <div class="flex flex-col pr-8">
            <h1
              class="font-bold text-3xl md:text-5xl tracking-tight mb-1 text-white"
            >
              Sagar Yadav
            </h1>
            <h2 class="text-gray-200 mb-4">
              Backend Developer (Python/Django) at
              <a
                href="https://crystaivf.com"
                target="_blank"
                class="font-semibold"
                >Crysta IVF</a
              >
            </h2>
            <!-- ?TODO - Add description -->
            <p class="text-gray-400 mb-16">
              Helping developers build a faster web. Teaching about web
              development, serverless, and React / Next.js.
            </p>
          </div>
          <div class="w-[80px] sm:w-[176px] relative mb-8 sm:mb-0 mr-auto">
            <img
              alt="Sagar Yadav"
              height="{176}"
              width="{176}"
              src=""
              class="rounded-full filter grayscale"
            />
          </div>
        </div>
        <h3
          class="font-bold text-2xl md:text-4xl tracking-tight mb-6 text-white"
        >
          Featured Posts
        </h3>
        <div class="flex gap-6 flex-col md:flex-row">
          <BlogPostCard
            title="Everything I Know About Style Guides, Design Systems, and Component Libraries"
            slug="style-guides-component-libraries-design-systems"
          />

          <BlogPostCard
            title="Rust Is The Future of JavaScript Infrastructure"
            slug="rust"
          />
          <BlogPostCard
            title="Past, Present, and Future of React State Management"
            slug="react-state-management"
          />
        </div>
        <NuxtLink to="/blog">
          <a
            class="flex mt-8 text-gray-400 leading-7 rounded-lg hover:text-gray-200 transition-all h-6"
          >
            Read all posts
            <svg
              xmlns="http://www.w3.org/2000/svg"
              fill="none"
              viewBox="0 0 24 24"
              class="h-6 w-6 ml-1"
            >
              <path
                stroke="currentColor"
                strokeLinecap="round"
                strokeLinejoin="round"
                strokeWidth="{2}"
                d="M17.5 12h-15m11.667-4l3.333 4-3.333-4zm3.333 4l-3.333 4 3.333-4z"
              />
            </svg>
          </a>
        </NuxtLink>
      </div>
      <Footer />
    </main>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  name: 'IndexPage',
  head() {
    return {
      title: 'Sagar Yadav | Backend Developer',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content:
            "This is Sagar Yadav's personal website. Here you can find his blog posts and resume.",
        },
      ],
    }
  },
})
</script>
