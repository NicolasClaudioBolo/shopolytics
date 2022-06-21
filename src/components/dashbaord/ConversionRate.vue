<template>
  <div class="text-gray-500 text-xs font-semibold mb-3">CONVERSION RATE</div>
  <div class="bg-white border shadow rounded w-full h-full overflow-hidden py-2 px-6 flex items-center justify-between">
    <div class="flex flex-col justify-center">
      <div class="flex flex-col justify-between">
        <div class="flex items-center">
          <img class="w-5 mr-2" :src="asset('images/info.svg')" alt="" srcset="">
          <div class="text-sm text-gray-500 mr-1">All channels</div>
          <img :src="asset('images/chevron-right.svg')" alt="" srcset="">
        </div>
        <div class="text-2xl font-semibold mt-2">4.38%</div>
      </div>
    </div>
    <bar-chart
      :bar-width="4"
    />
  </div>
</template>

<script>
import BarChart from './BarChart.vue'
export default {
  name: 'ConversionRate',
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