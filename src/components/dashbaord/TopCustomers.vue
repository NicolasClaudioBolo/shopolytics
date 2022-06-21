<template>
  <div class="relative">
    <div class="text-gray-500 text-xs font-semibold mb-3">TOP 3 CUSTOMERS</div>
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
  <div class="w-full border bg-white shadow chart-container h-full">
    <div class="flex items-center p-4">
      <div class="flex items-center w-full sticky top-0 bg-white">
        <div class="w-full h-full flex items-center">
          <div class="text-xs text-gray-500 mr-4">NAME</div>
        </div>
      </div>
      <div class="flex items-center w-full sticky top-0 bg-white">
        <div class="w-full h-full flex items-center">
          <div class="text-xs text-gray-500 mr-4">REVENUE</div>
        </div>
      </div>
      <div class="flex items-center w-full sticky top-0 bg-white">
        <div class="w-full h-full flex items-center">
          <div class="text-xs text-gray-500 mr-4">LAST ORDER</div>
        </div>
      </div>
      <div class="flex items-center w-full sticky top-0 bg-white">
        <div class="w-full h-full flex items-center">
          <div class="text-xs text-gray-500 mr-4"># OF ORDERS</div>
        </div>
      </div>
    </div>
    <div class="flex items-center w-full text-xs text-gray-500 px-4 py-1" v-for="(item, i) in items" :key="item" :class="{'bg-gray-100': i % 2 === 0}">
      <div class="w-full h-full flex items-center">
        {{item.name}}
      </div>
      <div class="w-full h-full flex items-center">
        {{item.revenue}}
      </div>
      <div class="w-full h-full flex items-center">
        {{item.lastOrder}}
      </div>
      <div class="w-full h-full flex items-center">
        {{item.numOfOrders}}
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
          name: 'Juan Rodriguez',
          revenue: '$123,23',
          lastOrder: '03/12/2021',
          numOfOrders: '12x'
         
        },
        {
          name: 'Michael Frost',
          revenue: '$123,23',
          lastOrder: '03/12/2021',
          numOfOrders: '12x'
         
        },
        {
          name: 'Robert Plant',
          revenue: '$123,23',
          lastOrder: '03/12/2021',
          numOfOrders: '12x'
         
        }
      ],
      daySelected: true
    }
  },
  methods: {
    toggleDays () {

    }
  }
}
</script>

<style>
.toggle-days-seven {
  top: -14px;
  right: 70px;
}
.toggle-days-year {
  top: -14px;
}

</style>