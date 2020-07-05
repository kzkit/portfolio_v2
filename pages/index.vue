<template>
  <div
    class="overflow-hidden dark:bg-blue-900 transition duration-500 ease-in-out"
  >
    <Nav />
    <Header />
    <About />
    <Skill />
    <Footer />
  </div>
</template>

<script>
import Nav from "@/components/nav";
import Header from "@/components/header";
import About from "@/components/about";
import Skill from "@/components/skill";
import Footer from "@/components/footer";

export default {
  components: {
    Nav,
    Header,
    About,
    Skill,
    Footer
  },
  head() {
    return {
      title: `Zhen Kit`,
      meta: [
        {
          hid: "description",
          name: "description",
          content: "Zhen Kit personal website"
        }
      ]
    };
  }
};
</script>

<style></style>
