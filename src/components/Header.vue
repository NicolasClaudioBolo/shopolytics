<template>
  <div class="flex flex-col w-full">
    <div class="w-full h-14 bg-white border flex items-center justify-between">
      <div class="flex items-center">
        <div class="bg-gray-200 w-7 h-7 rounded-full cover flex justify-center items-center ml-5">
          <img class="z-10" :src="asset('images/store.svg')" alt="" srcset="">
        </div>
        <div class="text-black ml-2">Store Number 1</div>
        <img class="w-4 ml-1 mb-0.5 cursor-pointer" :src="asset('images/chevron-down.svg')" alt="" srcset="">
        <div class="flex border-2 rounded items-center ml-5">
          <button class="flex items-center justify-center px-4">
            <img :src="asset('images/search.svg')" alt="" srcset="">
          </button>
          <input
            type="text"
            class="search-input px-2 py-1 w-60"
            placeholder="Search everithing"
          />
        </div>
      </div>
      <img class="mr-6" :src="asset('images/user.svg')" alt="" srcset="">
    </div>
    <div class="w-full h-14 bg-white border border-t-0 flex items-center justify-between">
      <div class="text-lg ml-5">Dashboard</div>
      <div class="w-36 h-8 border mr-6 flex items-center justify-between rounded-md">
        <div class="text-xs text-gray-500 ml-2"> Last three days </div>
        <div class="w-0.5 h-full bg-gray-200" />
        <img class="mr-2" :src="asset('images/calendar.svg')" alt="" srcset="">
      </div>
    </div>
  </div>
</template>

<script>
// export default {
//   name: 'Header',
//   methods: {
//     asset: window.Vapor.asset
//   }
// }
</script>

<style scoped>

</style>