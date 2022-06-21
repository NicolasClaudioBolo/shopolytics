<template>
  <div class="text-gray-500 text-xs font-semibold mb-3">NET SALES, ORDERS, ITEMS</div>
  <div class="w-full border bg-white shadow chart-container p-3">
    <div class="flex justify-between">
      <div class="chart">
        <net-sales-chart/>
      </div>
      <div class="chart-card flex flex-col justify-center">
        <div 
          class="border bg-white xl:w-64 md:w-48 lg:w-48 sm:w-28 h-20 rounded-md p-3 mb-3 hover:bg-gray-100 relative card"
          :class="{'card-selected': sales, 'bg-gray-100': sales}"
        >
          <div class="flex justify-between">
            <div class="flex items-center">
              <span class="mr-2">$12,3000</span>
              <span class="text-gray-400 text-sm">+21.4%</span>
            </div>
            <input type="checkbox" name="" id="" class="checkbox" v-model="sales">
          </div>
          <div class="flex items-center mt-4">
            <img :src="asset('images/bill.svg')" alt="" srcset="">
            <span class="text-gray-500 text-sm ml-2">Net Sales</span>
          </div>
        </div>
        <div 
          class="border bg-white xl:w-64 md:w-48 lg:w-48 sm:w-28 h-20 rounded-md p-3 mb-3 hover:bg-gray-100 relative card"
          :class="{'card-selected': orders, 'bg-gray-100': orders}"
        >
          <div class="flex justify-between">
            <div class="flex items-center">
              <span class="mr-2">1,234</span>
              <span class="text-gray-400 text-sm">+1.3%</span>
            </div>
            <input type="checkbox" name="" id="" class="checkbox" v-model="orders">
          </div>
          <div class="flex items-center mt-4">
            <img :src="asset('images/cart.svg')" alt="" srcset="">
            <span class="text-gray-500 text-sm ml-2">Number of orders</span>
          </div>
        </div>
        <div 
          class="border bg-white xl:w-64 md:w-48 lg:w-48 sm:w-28 h-20 rounded-md p-3 mb-3 hover:bg-gray-100 relative card"
          :class="{'card-selected': items, 'bg-gray-100': items}"
        >
          <div class="flex justify-between">
            <div class="flex items-center">
              <span class="mr-2">876</span>
              <span class="text-gray-400 text-sm">+21.7%</span>
            </div>
            <input type="checkbox" name="" id="" class="checkbox" v-model="items">
          </div>
          <div class="flex items-center mt-4">
            <img :src="asset('images/box.svg')" alt="" srcset="">
            <span class="text-gray-500 text-sm ml-2">number of items</span>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import NetSalesChart from './NetSalesChart.vue'
export default {
  name: 'NetSales',
  components: {
    NetSalesChart
  },
  data () {
    return {
      sales: false,
      orders: false,
      items: false
    }
  },
  methods: {
    asset: window.Vapor.asset
  }
}
</script>

<style scoped>
.chart-container {
  height: 400px;
}
.chart {
  width: 56%;
}
:hover.card {
  box-shadow: -4px 0px 0px grey;
}
.card-selected {
  box-shadow: -4px 0px 0px grey;
}

</style>