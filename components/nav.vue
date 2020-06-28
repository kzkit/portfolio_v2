<template>
  <nav class="flex justify-between">
    <div></div>
    <div>
      <ul class="flex">
        <li class="mr-6 mt-6">
          <a
            class="font-sans font-semibold dark:text-white inline-block transition duration-500 ease-in-out hover:text-yellow-500 text-xl"
            href="#"
          >Home</a>
        </li>
        <li class="mt-6">
          <a
            class="font-sans font-semibold inline-block transition duration-500 ease-in-out hover:text-yellow-500 text-xl dark:text-white"
            href="#"
          >Blog</a>
        </li>
      </ul>
    </div>
    <div class="mr-6 mt-6">
      <button @click="toggleDarkMode">
        <img
          class="w-3/4 fill-current dark:text-white"
          src="../assets/img/icons8-sun.svg"
          alt="dark_mode_toggle"
        />
      </button>
    </div>
  </nav>
</template>

<script>
export default {
  methods: {
    toggleDarkMode() {
      this.$colorMode.preference =
        this.$colorMode.value == "light" ? "dark" : "light";

      if (this.$colorMode.preference == "light") {
        this.isLight = true;
      } else {
        this.isLight = false;
      }
    }
  },
  data() {
    return {
      isLight: true
    };
  }
};
</script>

<style></style>
