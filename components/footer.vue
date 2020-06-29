<template>
  <footer>
    <div class="mb-1 pb-1 pl-2 relative">
      <p
        class="font-sans font-mediumtext-xl text-gray-800 dark:text-gray-300 transition duration-500 ease-in-out"
      >
        Inspired by
        <a
          class="half_background font-semibold"
          href="https://www.behance.net/KuangC"
        >KuangC</a>
      </p>
      <button @click="scrollToTop" class="absolute bottom-0 right-0 mb-1 mr-2">
        <img class="xl:w-8 xxl:w-8" src="../assets/img/icon-up.png" alt="go Up" />
      </button>
    </div>
  </footer>
</template>

<script>
export default {
  methods: {
    scrollToTop() {
      window.scrollTo({
        top: 0,
        left: 0,
        behavior: "smooth"
      });
    }
  }
};
</script>

<style>
</style>