<template>
  <div class="flex items-end h-20">
    <div 
      v-for="item in items" 
      :key="item" 
      class="bg-gray-200 hover:bg-gray-300 rounded-t-md mx-0.5 relative" 
      :class="[item.height, `w-${barWidth}`]"
      @mouseover="selected = item.id"
      @mouseleave="selected = ''"
    >
      <div class="absolute border bg-white h-12 w-24 shadow tooltip p-1 z-10" v-if="selected === item.id">
        <div class="text-sm">{{item.amount}}</div>
        <div class="text-xs text-gray-400">{{item.date}}, {{item.time}}</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'BarChart',
  props: {
    barWidth: {
      type: Number,
      default: 2
    }
  },
  data() {
    return {
      items: [
        {
          id: '1',
          height: 'h-20',
          date: 'Sep 13',
          time: '15:00',
          amount: '1,235'
        },
        {
          id: '2',
          height: 'h-16',
          date: 'Sep 14',
          time: '15:00',
          amount: '1,235'
        },
        {
          id: '3',
          height: 'h-16',
          date: 'Sep 15',
          time: '15:00',
          amount: '1,235'
        },
        {
          id: '4',
          height: 'h-20',
          date: 'Sep 16',
          time: '15:00',
          amount: '1,235'
        },
        {
          id: '5',
          height: 'h-16',
          date: 'Sep 17',
          time: '15:00',
          amount: '1,235'
        },
        {
          id: '6',
          height: 'h-16',
          date: 'Sep 18',
          time: '15:00',
          amount: '1,235'
        },
        {
          id: '7',
          height: 'h-16',
          date: 'Sep 19',
          time: '15:00',
          amount: '1,235'
        },
        {
          id: '8',
          height: 'h-16',
          date: 'Sep 20',
          time: '15:00',
          amount: '1,235'
        },
        {
          id: '9',
          height: 'h-14',
          date: 'Sep 21',
          time: '15:00',
          amount: '1,235'
        },
        {
          id: '10',
          height: 'h-16',
          date: 'Sep 22',
          time: '15:00',
          amount: '1,235'
        },
        {
          id: '11',
          height: 'h-16',
          date: 'Sep 23',
          time: '15:00',
          amount: '1,235'
        },
      ],
      selected: ''
    }
  },
  mounted() {
    
  }
}
</script>

<style scoped>
.tooltip {
  top: -47px;
  left: -30px;
  z-index: 200;
}

</style>