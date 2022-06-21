<template>
  <div class="text-gray-500 text-xs font-semibold mb-3">SELECT STORE METRICS</div>
   <div class="w-full bg-white shadow border rounded h-60 flex flex-col items-center overflow-auto p-5">
      <div class="flex justify-between items-between w-full mt-2 text-gray-500" v-for="(item, i) in items" :key="item" :class="{'mb-2': i !== items.length - 1}">
        <div class="flex items-center">
          <img :src="asset(`images/${item.icon}.svg`)" alt="" srcset="">
          <div class="ml-2 text-sm">{{item.text}}</div>
        </div>
        <div class="text font-semibold text-black">{{item.value}}</div>
      </div>
   </div>
</template>

<script>
export default {
  name: 'StoreMetrics',
  data () {
    return {
      items: [
        {
          icon: 'bill',
          text: 'Net Sales per visitor',
          value: '$1.50'
        },
        {
          icon: 'cart',
          text: 'Cart abandonment rate',
          value: '72%'
        },
        {
          icon: 'checkbox',
          text: 'Checkout completion rate',
          value: '99%'
        },
        {
          icon: 'clock',
          text: 'Avrg. time on site',
          value: '01:44'
        },
        {
          icon: 'clock',
          text: 'Avrg. order compl. time',
          value: '02:30'
        },
      ]
    }
  },
  methods: {
    asset: window.Vapor.asset
  }
}
</script>

<style>

</style>