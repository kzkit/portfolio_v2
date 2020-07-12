<template>
  <nav class="flex justify-between">
    <div></div>
    <div class="pl-12">
      <ul class="flex">
        <li class="mr-6 mt-6">
          <nuxt-link to="/">
            <p
              class="font-sans font-semibold dark:text-white inline-block transition duration-500 ease-in-out hover:text-yellow-500 text-xl xl:text-xl xxl:text-2xl"
            >Home</p>
          </nuxt-link>
        </li>
        <li class="mt-6">
          <nuxt-link to="blogs">
            <p
              class="font-sans font-semibold inline-block transition duration-500 ease-in-out hover:text-yellow-500 text-xl dark:text-white xl:text-xl xxl:text-2xl"
            >Blog</p>
          </nuxt-link>
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
