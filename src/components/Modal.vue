<template>
  <div class="">
    <h1 class="text-2xl font-semibold text-blue-500">Modal</h1>
    <button @click="isOpen = !isOpen" class="bg-gray-900 text-gray-200 mx-5 shadow-xl w-32 h-10 rounded-lg outline-none appearance-none hover:bg-gray-800">Login</button>
    <button @click="isOpenRegister = !isOpenRegister" class="bg-gray-900 text-gray-200 mx-5 shadow-xl w-32 h-10 rounded-lg outline-none appearance-none hover:bg-gray-800">Register</button>
    <button @click="notification = !notification" class="bg-gray-900 text-gray-200 mx-5 shadow-xl w-32 h-10 rounded-lg outline-none appearance-none hover:bg-gray-800">Notify</button>
    <div @click="isOpen = false" v-if="isOpen" class="absolute bg-gray-800 opacity-50  inset-0 px-4 pb-4 sm:inset-0 sm:flex sm:items-center sm:justify-center"></div>
    <div @click="isOpenRegister = false" v-if="isOpenRegister" class="absolute bg-gray-800 opacity-50  inset-0 px-4 pb-4 sm:inset-0 sm:flex sm:items-center sm:justify-center"></div>
    <div @click="notification = false" v-if="notification" class="absolute bg-gray-800 opacity-0  inset-0 px-4 pb-4 sm:inset-0 sm:flex sm:items-center sm:justify-center"></div>
    <transition name="fade">
      <div v-if="isOpen" class="mx-auto fixed inset-0 mt-24 z-10 rounded-t-xxxl flex flex-col items-center justify-center space-y-4 bg-gray-300">
        <span class="w-20 h-1 bg-gray-500 top-0 absolute mt-5 rounded-full mx-auto"></span>
      <h1 class="text-2xl mb-10 font-semibold">Login</h1>
      <input class="w-64 h-10 rounded-lg bg-white border appearance-none outline-none px-3 focus:border-blue-500 shadow sm:w-80" type="email" placeholder="email address" required />
      <input class="w-64 h-10 rounded-lg bg-white border appearance-none outline-none px-3 focus:border-blue-500 shadow sm:w-80" type="password" placeholder="password" required />
      <button class="w-64 h-10 rounded-lg text-white bg-black shadow-lg sm:w-80">Submit</button>
    </div>
    </transition>
    <transition name="fade">
      <div v-if="isOpenRegister" class="mx-auto fixed inset-0 mt-24 z-10 rounded-t-xxxl flex flex-col items-center justify-center space-y-4 bg-gray-300">
        <span class="w-20 h-1 bg-gray-500 top-0 absolute mt-5 rounded-full mx-auto"></span>
      <h1 class="text-2xl mb-10 font-semibold">Register</h1>
      <input class="w-64 h-10 rounded-lg bg-white border appearance-none outline-none px-3 focus:border-blue-500 shadow sm:w-80" type="email" placeholder="email address" required />
      <input class="w-64 h-10 rounded-lg bg-white border appearance-none outline-none px-3 focus:border-blue-500 shadow sm:w-80" type="password" placeholder="password" required />
      <button class="w-64 h-10 rounded-lg text-white bg-black shadow-lg sm:w-80">Submit</button>
    </div>
    </transition>
    <transition name="notify-fade">
      <div v-if="notification" class="mx-auto border-green-500 border fixed z-10 mt-5 rounded bg-green-100 right-0 top-0 shadow-lg w-80">
        <!-- <span class="w-20 h-1 bg-gray-500 top-0 absolute mt-5 rounded-full mx-auto"></span> -->
        <span @click="notification = false" v-if="notification" class="text-2xl text-green-700 float-right mr-3 cursor-pointer">&times;</span>
      <p class="text-base my-5 font-semibold">I'm a notification</p>
    </div>
    </transition>
  </div>
</template>

<script>
export default {
  name: "Modal",
  data() {
    return {
      isOpen: false,
      isOpenRegister: false,
      notification: true
    }
  },
  methods: {}
};
</script>

<style lang="scss" scoped>
.fade-enter-active, .fade-leave-active{
  transition: 0.3s ease-in-out;
}
.fade-enter, .fade-leave-to{
  opacity: 0;
  transform: translateY(500px);
}
.notify-fade-enter-active, .notify-fade-leave-active{
  transition: 0.3s ease-in-out;
}
.notify-fade-enter, .notify-fade-leave-to{
  opacity: 0;
  transform: translateX(300px);
}
</style>