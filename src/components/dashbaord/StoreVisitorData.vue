<template>
  <div class="text-gray-500 text-xs font-semibold mb-3">STORE VISITOR DATA</div>
  <div class="w-full bg-white shadow border rounded h-60 p-6 flex flex-col justify-center">
    <div class="flex items-center justify-between my-3">
      <div class="flex flex-col justify-center">
        <div class="flex">
          <span class="text-gray-500 text sm">Number of visitors</span>
          <img :src="asset('images/chevron-right.svg')" alt="" srcset="">
        </div>
        <div class="text-2xl mt-2">2,345</div>
      </div>
      <bar-chart/>
    </div>
    <div class="flex items-center justify-between my-3">
      <div class="flex flex-col justify-center">
        <div class="flex">
          <span class="text-gray-500 text sm">Number of visitors</span>
          <img :src="asset('images/chevron-right.svg')" alt="" srcset="">
        </div>
        <div class="text-2xl mt-2">2,345</div>
      </div>
      <bar-chart/>
    </div>
  </div>
</template>

<script>
import BarChart from './BarChart.vue'
export default {
  name: 'StoreVisitorData',
  components: {
    BarChart
  },
  methods: {
    asset: window.Vapor.asset
  }
}
</script>

<style>

</style>