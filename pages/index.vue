<template>
  <div>
    <Nav />
    <div class="container mx-auto xl:h-screen">
      <Header />
    </div>
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
      title: "Zhen Kit"
    };
  }
};
</script>

<style>
.half_background {
  background: linear-gradient(to top, #ffe200 35%, transparent 30%);
}
</style>
