<template>
  <div class="bg-gray-100 min-h-screen flex">
    <navbar/>
    <div class="flex flex-col w-full">
      <header-app/>
      <slot></slot>
    </div>
  </div>
</template>

<script>
import Navbar from './components/Navbar.vue'
import Header from './components/Header.vue'
export default {
  name: 'Layout',
  components: {
    Navbar,
    'header-app': Header
  }

}
</script>

<style>

</style>