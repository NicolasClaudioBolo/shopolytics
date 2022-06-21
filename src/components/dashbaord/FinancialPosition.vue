<template>
  <div class="ml-4 w-full">
    <div class="text-gray-500 text-xs font-semibold mb-3">FINANCIAL POSITION</div>
    <div class="border bg-white shadow card">
      <div class="flex justify-between p-5">
        <div class="flex items-center">
          <div class="w-2 h-2 bg-gray-500 rounded-full"/>
          <img :src="asset('images/paypal.png')" class="w-20" alt="" srcset="">
        </div>
        <div class="text-gray-700">$76k</div>
      </div>
      <div class="flex justify-between p-5">
        <div class="flex items-center">
          <div class="w-2 h-2 bg-gray-500 rounded-full"/>
          <img :src="asset('images/stripe.png')" class="w-20" alt="" srcset="">
        </div>
        <div class="text-gray-700">$76k</div>
      </div>
      <div class="flex justify-between p-5">
        <div class="flex items-center">
          <div class="w-2 h-2 bg-gray-500 rounded-full mr-2"/>
          <img :src="asset('images/ing.png')" class="w-20" alt="" srcset="">
        </div>
        <div class="text-gray-700">$76k</div>
      </div>
      <div class="w-full flex justify-center">
        <div class="bg-gray-100 w-5/6 h-0.5" />
      </div>
      <div class="h-48 flex items-center justify-between">
        <div class="ml-6 w-28">
          <financial-chart/>
        </div>
        <span class="text-gray-600 mr-6 total-label">Total cash position</span>
      </div>
    </div>
  </div>
</template>

<script>
import FinancialChart from './FinancialChart.vue'
export default {
  name: 'FinancialPosition',
  components: {
    FinancialChart
  },
  methods: {
    asset: window.Vapor.asset
  }
}
</script>

<style scoped>
.card {
  height: 400px;
  margin-right: 15px;
}
.total-label {
  align-self: flex-start;
  margin-top: 40px;
}
</style>