<template>
  <div class="relative">
    <div class="text-gray-500 text-xs font-semibold mb-3">ORDER DATA</div>
    <div class="toggle-days-seven absolute cursor-pointer border border-gray-300 text-xs font-semibold mb-3 p-2 rounded-l-md" @click="daySelected = !daySelected"
      :class="{'bg-gray-300 text-gray-500': daySelected, 'text-gray-300': !daySelected}"
    >
      7 DAYS
    </div>
    <div class="toggle-days-year absolute cursor-pointer right-0 border border-gray-300 text-xs font-semibold mb-3 p-2 rounded-r-md" @click="daySelected = !daySelected" 
      :class="{'bg-gray-300 text-gray-500': !daySelected, 'text-gray-300': daySelected}"
    >
      365 DAYS
    </div>
  </div>
  <div class="bg-white border shadow rounded w-full h-full overflow-auto py-2 px-6">
    <div v-for="item in items" :key="item">
      <div class="flex justify-between items-center text-gray-600">
        <div class="flex items-center">
          <img class="w-4 mr-1" :src="asset(`images/${item.icon}.svg`)" alt="" srcset="">
          <div>{{item.text}}</div>
        </div>
        <div class="flex items-center mt-5">
          <div class="text-lg font-semibold">{{item.value}}</div>
          <div class="text-gray-500 ml-2 text-xs">+{{item.percentage}}</div>
        </div>
      </div>
    </div>
    <div class="bg-gray-100 h-0.5 w-full my-4"/>
    <div v-for="state in dataState" :key="state">
      <div class="flex justify-between items-center my-1">
        <div class="text-gray-500">{{state.text}}</div>
        <div class="flex items-center">
          <div>{{state.value}}</div>
          <div class="ml-1 text-xs text-gray-500">+{{state.percentage}}</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'OrderData',
  data () {
    return {
      daySelected: true,
      items: [
        {
          icon: 'info',
          text: 'Number of refunds',
          value: '24',
          percentage: '21.7%'
        },
        {
          icon: 'info',
          text: 'Of refunds',
          value: '$349',
          percentage: '21.7%'
        },
      ],
      dataState: [
        {
          text: 'Completed',
          value: '12,231',
          percentage: '21%'
        },
        {
          text: 'Processing',
          value: '121',
          percentage: '3%'
        },
        {
          text: 'Pending Payment',
          value: '9,833',
          percentage: '5%'
        },
        {
          text: 'Cancelled',
          value: '162',
          percentage: '12%'
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

</style>