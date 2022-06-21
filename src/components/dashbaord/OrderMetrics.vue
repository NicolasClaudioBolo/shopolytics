<template>
  <div class="text-gray-500 text-xs font-semibold mb-3">KEY AVERAGE ORDER METRICS TRENDS & DATA</div>
  <div class="w-full bg-white shadow border rounded h-full flex overflow-auto">
    <div class="w-2/3 h-full ml-3">
      <order-metrics-chart/>
    </div>
    <div class="chart-card flex flex-col justify-center">
        <div 
          class="border bg-white w-40 h-18 text-xs rounded-md p-3 mb-3 hover:bg-gray-100 relative card"
          :class="{'card-selected': order, 'bg-gray-100': order}"
        >
          <div class="flex justify-between items-center">
            <div class="flex items-center">
              <span class="mr-2 font-semibold">$12,3000</span>
              <span class="text-gray-400 text-xs">+21.4%</span>
            </div>
            <input type="checkbox" name="" id="" class="checkbox" v-model="order">
          </div>
          <div class="flex items-center mt-2">
            <img :src="asset('images/cart.svg')" alt="" srcset="">
            <span class="text-gray-500 text-sm ml-2">Order value</span>
          </div>
        </div>
        <div 
          class="border bg-white w-40 h-18 text-xs rounded-md p-3 mb-3 hover:bg-gray-100 relative card"
          :class="{'card-selected': items, 'bg-gray-100': items}"
        >
          <div class="flex justify-between items-center">
            <div class="flex items-center">
              <span class="mr-2 font-semibold">1,234</span>
              <span class="text-gray-400 text-xs">+1.3%</span>
            </div>
            <input type="checkbox" name="" id="" class="checkbox" v-model="items">
          </div>
          <div class="flex items-center mt-2">
            <img :src="asset('images/box.svg')" alt="" srcset="">
            <span class="text-gray-500 text-sm ml-2">Items</span>
          </div>
        </div>
    </div>
  </div>
</template>

<script>
import OrderMetricsChart from './OrderMetricsChart.vue'
export default {
  name: 'OrderMetrics',
  components: {
    OrderMetricsChart
  },
  data () {
    return {
      order: false,
      items: false
    }
  },
  methods: {
    asset: window.Vapor.asset
  }
}
</script>

<style>
:hover.card {
  box-shadow: -4px 0px 0px grey;
}
.card-selected {
  box-shadow: -4px 0px 0px grey;
}
</style>