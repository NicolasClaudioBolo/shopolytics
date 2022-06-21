<template>
  <div class="text-gray-500 text-xs font-semibold mb-3">TOP CHANNELS / REFERRERS</div>
   <div class="w-full bg-white shadow border rounded h-60 flex flex-col items-center overflow-auto">
     <div class="flex p-4 items-center w-full sticky top-0 bg-white">
       <div class="w-6/12 h-full flex items-center">
        <div class="text-xs text-gray-500 mr-4">NAME</div>
        <img class="cursor-pointer" :src="asset('images/sort.svg')" alt="" srcset="" @click="sort">
       </div>
       <div class="flex justify-center w-2/12 h-full">
        <div><img :src="asset('images/user.svg')" alt="" srcset=""></div>
       </div>
       <div class="flex justify-center w-2/12 h-full">
        <div><img :src="asset('images/cart.svg')" alt="" srcset=""></div>
       </div>
       <div class="flex justify-center w-2/12 h-full">
        <div><img :src="asset('images/marketing-performance.svg')" alt="" srcset=""></div>
       </div>
     </div>
     <div class="flex py-2 px-4 items-center w-full text-xs text-gray-500" v-for="(item, i) in items" :key="item" :class="{'bg-gray-100': i % 2 === 0}">
      <div class="w-6/12 h-full flex items-center">
        <div class="text-xs">{{item.name}}</div>
      </div>
      <div class="flex justify-center w-2/12 h-full">
        <div>{{item.users}}</div>
      </div>
      <div class="flex justify-center w-2/12 h-full">
        <div>{{item.buys}}</div>
      </div>
      <div class="flex justify-center w-2/12 h-full">
        <div>{{item.percentage}}</div>
      </div>
     </div>
  </div>
</template>

<script>
export default {
  name: 'TopChannels',
  data () {
    return {
      items: [
        {
          name: 'Instagram',
          users: '123',
          'buys': '23',
          percentage: '12%'
        },
        {
          name: 'Facebook',
          users: '123',
          'buys': '23',
          percentage: '12%'
        },
      ],
      order: false
    }
  },
  methods: {
    sort () {
      if (!this.order) this.items.sort((a,b) => (a.name > b.name) ? 1 : ((b.name > a.name) ? -1 : 0))
      else this.items.sort((a,b) => (b.name > a.name) ? 1 : ((a.name > b.name) ? -1 : 0))
      this.order = !this.order
    },
    asset: window.Vapor.asset
  }
}
</script>

<style>

</style>