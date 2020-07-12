<template>
  <div class="overflow-hidden dark:bg-blue-900 transition duration-500 ease-in-out h-full">
    <Nav />
    <div class="container mx-auto mb-56 mt-12 px-12">
      <h1
        class="font-bold text-4xl dark:text-gray-300 transition duration-500 ease-in-out"
      >Blog Posts ✏️</h1>
      <div class="mt-4">
        <ul class="flex flex-wrap">
          <li
            v-for="article of articles"
            :key="article.slug"
            class="w-full mb-6 xl:w-1/2 xxl:w-1/2"
          >
            <NuxtLink
              :to="{ name: 'blog-slug', params: { slug: article.slug } }"
              class="flex mx-2 rounded shadow-sm hover:shadow-xl xxl:flex-col dark:bg-white transition duration-500 ease-in-out"
            >
              <img
                v-if="article.img"
                class="h-48 xl:w-1/2 xxl:w-full object-cover"
                :src="article.img"
              />

              <div class="p-6 flex flex-col justify-between xl:w-1/2 xxl:w-full">
                <h2 class="font-bold">{{ article.title }}</h2>
                <p>by {{ article.author.name }}</p>
                <p class="font-bold text-gray-600 text-sm">{{ article.description }}</p>
              </div>
            </NuxtLink>
          </li>
        </ul>
      </div>
    </div>
    <Footer />
  </div>
</template>

<script>
import Nav from "@/components/nav";
import Footer from "@/components/footer";

export default {
  components: {
    Nav,
    Footer
  },
  async asyncData({ $content, params }) {
    const articles = await $content("articles", params.slug)
      .only(["title", "description", "img", "slug", "author"])
      .sortBy("createdAt", "desc")
      .fetch();
    return {
      articles
    };
  }
};
</script>

<style>
</style>