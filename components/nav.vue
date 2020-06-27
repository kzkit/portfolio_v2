<template>
  <nav class="flex justify-between">
    <div></div>
    <div>
      <ul class="flex">
        <li class="mr-6 mt-6">
          <a
            class="font-sans font-semibold inline-block transition duration-500 ease-in-out hover:text-yellow-500 text-xl"
            href="#"
          >Home</a>
        </li>
        <li class="mt-6">
          <a
            class="font-sans font-semibold inline-block transition duration-500 ease-in-out hover:text-yellow-500 text-xl"
            href="#"
          >Blog</a>
        </li>
      </ul>
    </div>
    <div class="mr-6 mt-6">
      <button @click="darkMode">
        <img class="w-3/4" src="../assets/img/icons8-sun.svg" alt="dark_mode_toggle" />
      </button>
    </div>
  </nav>
</template>

<script>
export default {};
</script>

<style>
</style>