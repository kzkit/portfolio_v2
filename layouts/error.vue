<template>
  <div
    class="container flex mx-auto my-auto xl:h-screen px-12 py-12 justify-center flex-col items-center"
  >
    <img class="w-64" src="../assets/img/404.png" alt="error_404" />
    <p
      class="text-center font-sans font-extrabold text-3xl xl:text-6xl text-gray-800 mt-12 half_background"
    >Page Not Found</p>
    <nuxt-link
      class="text-center font-sans text-xl xl:text-4xl font-bold text-gray-800 mt-12 rounded-full py-2 px-4 border-2 transition duration-500 ease-in-out hover:bg-yellow-400 transform hover:-translate-y-1 hover:scale-110"
      to="/"
    >Go back</nuxt-link>
  </div>
</template>

<script>
export default {};
</script>

<style>
</style>