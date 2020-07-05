<template>
  <div>
    <Nav />
    <div class="container mx-auto h-screen">
      <article>
        <h1>{{ article.title }}</h1>
        <nuxt-content :document="article" />
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
          content: "Article"
        }
      ]
    };
  }
};
</script>

<style></style>
