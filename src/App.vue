<template>
  <div id="app">
    <div class="">
      <div class="flex flex-row items-center justify-center w-80 mx-auto">
        <img class="h-10" alt="Vue logo" src="./assets/logo.png" />
        <h1 class="text-xl font-bold">Tailwind-Vue components</h1>
      </div>
    </div>
    <Modal />
  </div>
</template>

<script>
import Modal from "./components/Modal.vue";

export default {
  name: "App",
  components: {
    Modal
  }
};
</script>

<style lang="scss">

</style>
