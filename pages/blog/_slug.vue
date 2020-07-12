<template>
  <div class="overflow-hidden dark:bg-blue-900 transition duration-500 ease-in-out h-auto">
    <Nav />
    <div class="container mx-auto mb-12">
      <article>
        <h1
          class="pt-12 text-center font-sans font-extrabold text-3xl xl:text-4xl xxl:text-6xl text-gray-800 dark:text-gray-300 transition duration-500 ease-in-out"
        >{{ article.title }}</h1>
        <h2
          class="text-center text-gray-800 dark:text-gray-300 transition duration-500 ease-in-out"
        >{{ formatDate(article.createdAt) }}</h2>
        <h2
          class="text-center text-gray-800 dark:text-gray-300 transition duration-500 ease-in-out"
        >Written by {{ article.author.name }}</h2>
        <div class="container mx-auto px-12 flex justify-center mt-12">
          <img class="w-6/12" :src="article.img" :alt="article.alt" />
        </div>
        <nuxt-content
          class="container mx-auto mt-12 px-12 dark:text-gray-300 transition duration-500 ease-in-out"
          :document="article"
        />
      </article>
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
    const article = await $content("articles", params.slug).fetch();

    return { article };
  },
  methods: {
    formatDate(date) {
      const options = { year: "numeric", month: "long", day: "numeric" };
      return new Date(date).toLocaleDateString("en", options);
    }
  },
  head() {
    return {
      title: `Article 1 - Zhen Kit`,
      meta: [
        {
          hid: "description",
          name: "description",
          content: "article by zhen kit"
        }
      ]
    };
  }
};
</script>

<style>
.nuxt-content h1 {
  @apply text-2xl font-bold font-sans;
}

.nuxt-content h2 {
  @apply text-xl font-bold font-sans;
}

.nuxt-content h3 {
  @apply text-xl font-bold font-sans;
}

.nuxt-content p {
  font-size: 1rem;
}
</style>
