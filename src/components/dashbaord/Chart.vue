<template>
  <div class="text-gray-500 text-xs font-semibold mb-3">CHART</div>
  <div class="w-full border bg-white shadow chart-container h-full">
    <div class="flex items-center p-4">
      <div class="flex items-center w-full sticky top-0 bg-white">
        <div class="w-4/12 h-full flex items-center">
          <div class="text-xs text-gray-500 mr-4">NAME</div>
          <img class="cursor-pointer" :src="asset('images/sort.svg')" alt="" srcset="" @click="sort('orderName')">
        </div>
      </div>
      <div class="flex items-center w-full sticky top-0 bg-white justify-center">
        <div class="w-4/12 h-full flex items-center">
          <div class="text-xs text-gray-500 mr-4">REVENUE</div>
          <img class="cursor-pointer" :src="asset('images/sort.svg')" alt="" srcset="" @click="sort('orderRevenue')">
        </div>
      </div>
      <div class="flex items-center w-full sticky top-0 bg-white justify-end">
        <div class="w-4/12 h-full flex items-center">
          <div class="text-xs text-gray-500 mr-4">AOV</div>
          <img class="cursor-pointer" :src="asset('images/sort.svg')" alt="" srcset="" @click="sort('orderAov')">
        </div>
      </div>
    </div>
    <div class="flex items-center w-full text-xs text-gray-500 px-4 py-1" v-for="(item, i) in items" :key="item" :class="{'bg-gray-100': i % 2 === 0}">
      <div class="w-4/12 h-full flex items-center">
        {{item.name}}
      </div>
      <div class="w-4/12 h-full flex items-center justify-center">
        <div class="text-lg text-gray-500">{{item.revenue.max}}</div>
        <div class="text-gray-400 ml-1 text-sm">| {{item.revenue.min}}</div>
      </div>
      <div class="w-4/12 h-full flex items-center justify-end">
        <div class="text-lg text-gray-500">{{item.aov.max}}</div>
        <div class="text-gray-400 ml-1 text-sm">| {{item.aov.min}}</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Chart',
  data () {
    return {
      items: [
        {
          name: 'New Customers',
          revenue: {
            max: '$3,200',
            min: '$1,900'
          },
          aov: {
            max: '$36,50',
            min: '$21,40'
          }
        },
        {
          name: 'Existing Customers',
          revenue: {
            max: '$3,200',
            min: '$1,900'
          },
          aov: {
            max: '$36,50',
            min: '$21,40'
          }
        },
        {
          name: 'Average Order Items',
          revenue: {
            max: '$3,200',
            min: '$1,900'
          },
          aov: {
            max: '$36,50',
            min: '$21,40'
          }
        }
      ],
      orderName: false,
      orderRevenue: false,
      orderAov: false,
    }
  },
  methods: {
    sort (label) {
      if (label === 'orderName') {
        if (!this[label]) this.items.sort((a,b) => (a.name > b.name) ? 1 : ((b.name > a.name) ? -1 : 0))
        else this.items.sort((a,b) => (b.name > a.name) ? 1 : ((a.name > b.name) ? -1 : 0))
        this[label] = !this[label]
      }
    },
    asset: window.Vapor.asset
  }
}
</script>

<style>

</style>