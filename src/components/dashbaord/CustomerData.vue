<template>
  <div class="text-gray-500 text-xs font-semibold mb-3">CUSTOMER DATA</div>
  <div class="w-full border bg-white shadow chart-container py-4 px-7 h-full flex justify-between">
    <div class="flex flex-col justify-between h-full">
      <div v-for="item in items" :key="item">
        <div class="flex items-center">
          <img class="w-4 mr-1" :src="asset(`images/${item.icon}.svg`)" alt="">
          <div class="text-sm text-gray-500">{{item.name}}</div>
        </div>
        <div class="text-2xl font-semibold" :class="{'text-gray-500': item.name === 'New Customers'}">{{item.value}}</div>
      </div>
    </div>
    <div class="self-center relative mr-8">
      <div class="w-24">
        <customer-data-chart/>
      </div>
      <div class="absolute legends">
        <div class="flex items-center">
          <div class="bg-gray-500 h-2 w-2"/>
          <div class="text-xs text-gray-700 ml-1 mb-1">25%</div>
        </div>
        <div class="flex items-center">
          <div class="bg-gray-900 h-2 w-2"/>
          <div class="text-xs text-gray-700 ml-1">75%</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import CustomerDataChart from './CustomerDataChart.vue'
export default {
  name: 'CustomerData',
  components: {
    CustomerDataChart
  },
  data () {
    return {
      items: [
        {
          name: 'New Customers',
          value: '580',
          icon: 'add-user',
          percentage: '25%'
        },
        {
          name: 'Existing Customers',
          value: '1,932',
          icon: 'check-user',
          percentage: '75%'
        }
      ]
    }
  },
  methods: {
    asset: window.Vapor.asset
  }
}
</script>

<style>
.legends {
  top: 27px;
  right: -47px;
}
</style>