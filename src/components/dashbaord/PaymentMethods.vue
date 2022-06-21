<template>
  <div class="text-gray-500 text-xs font-semibold mb-3">PAYMENT METHODS</div>
  <div class="bg-white w-100 h-full shadow border rounded overflow-auto">
     <div class="flex items-center p-4 sticky top-0 bg-white z-10">
      <div class="flex items-center w-full sticky top-0 bg-white">
        <div class="w-full h-full flex items-center">
          <div class="text-xs text-gray-500 mr-4">PAYMENT</div>
        </div>
      </div>
      <div class="flex items-center w-full sticky top-0 bg-white">
        <div class="w-full h-full flex items-center">
          <div class="text-xs text-gray-500 mr-4"># OF ORDERS</div>
        </div>
      </div>
      <div class="flex items-center w-full sticky top-0 bg-white">
        <div class="w-full h-full flex items-center">
          <div class="text-xs text-gray-500 mr-4">NET SALES</div>
        </div>
      </div>
      <div class="flex items-center w-full sticky top-0 bg-white">
        <div class="w-full h-full flex items-center">
        </div>
      </div>
    </div>
    <div class="flex items-center w-full text-gray-500 px-4 py-1" v-for="(item, i) in items" :key="item" :class="{'bg-gray-100': i % 2 === 0}">
      <div class="w-full h-full flex items-center">
        <img class="logo-img" :src="asset(`images/${item.logo}.png`)" alt="">
      </div>
      <div class="w-full h-full flex items-center">
        <div class="text-lg">{{item.numOfOrders.max}}</div>
        <div class="text-gray-400 ml-1 text-sm">| {{item.numOfOrders.min}}</div>
      </div>
      <div class="w-full h-full flex items-center">
        <div class="text-lg">{{item.netSales.max}}</div>
        <div class="text-gray-400 ml-1 text-sm">| {{item.netSales.min}}</div>
      </div>
      <div class="w-full h-full flex items-center">
        <div class="text-lg">{{item.percentage.max}}</div>
        <div class="text-gray-400 ml-1 text-sm">| {{item.percentage.min}}</div>
      </div>
    </div>
    <div class="flex items-center w-full text-gray-500 px-4 py-1 sticky bottom-0 bg-white shadow-sm">
      <div class="w-full h-full flex items-center text-lg text-black font-semibold">
        TOTAL
      </div>
      <div class="w-full h-full flex items-center">
        <div class="text-lg">{{numberWithCommas(totalOrdersMax)}}</div>
        <div class="text-gray-400 ml-1 text-sm">| {{numberWithCommas(totalOrdersMin)}}</div>
      </div>
      <div class="w-full h-full flex items-center">
        <div class="text-lg">${{numberWithCommas(totalSalesMax)}}</div>
        <div class="text-gray-400 ml-1 text-sm">| ${{numberWithCommas(totalSalesMin)}}</div>
      </div>
      <div class="w-full h-full flex items-center">
        <div class="text-lg">{{totalPercentageMax}}%</div>
        <div class="text-gray-400 ml-1 text-sm">| {{totalPercentageMin}}%</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'PaymentMethods',
  data () {
    return {
      items: [
        {
          logo: 'ing',
          numOfOrders: {
            max: '2,300',
            min: '2,170'
          },
          netSales: {
            max: '$36,150',
            min: '$29,549'
          },
          percentage: {
            max: '21.9%',
            min: '20.9%'
          }
        },
        {
          logo: 'ing',
          numOfOrders: {
            max: '2,400',
            min: '2,170'
          },
          netSales: {
            max: '$36,150',
            min: '$29,549'
          },
          percentage: {
            max: '21.9%',
            min: '20.9%'
          }
        },
        {
          logo: 'ing',
          numOfOrders: {
            max: '2,100',
            min: '2,170'
          },
          netSales: {
            max: '$36,150',
            min: '$29,549'
          },
          percentage: {
            max: '21.9%',
            min: '20.9%'
          }
        },
        {
          logo: 'ing',
          numOfOrders: {
            max: '2,900',
            min: '2,170'
          },
          netSales: {
            max: '$36,150',
            min: '$29,549'
          },
          percentage: {
            max: '21.9%',
            min: '20.9%'
          },
        },
        {
          logo: 'ing',
          numOfOrders: {
            max: '2,900',
            min: '2,170'
          },
          netSales: {
            max: '$36,150',
            min: '$29,549'
          },
          percentage: {
            max: '2.9%',
            min: '1.9%'
          },
        }
      ],
      totalOrdersMax: 0,
      totalOrdersMin: 0,
      totalSalesMax: 0,
      totalSalesMin: 0,
      totalPercentageMax: 0,
      totalPercentageMin: 0
    }
  },
  computed: {
    orderMaxFormatted() {
      return this.numberWithCommas(this.totalOrdersMax)
    }
  },
  methods: {
    calcTotalOrders () {
      this.items.forEach(item => {
        const ordersValue = parseFloat(item.numOfOrders.max.replace(/,/g, ''))
        this.totalOrdersMax += ordersValue
        const ordersValueMin = parseFloat(item.numOfOrders.min.replace(/,/g, ''))
        this.totalOrdersMin += ordersValueMin
        const salesValue = parseFloat(item.netSales.max.replace(/\$|,/g, ''))
        this.totalSalesMax += salesValue
        const salesValueMin = parseFloat(item.netSales.min.replace(/\$|,/g, ''))
        this.totalSalesMin += salesValueMin
        const percentageValue = parseFloat(item.percentage.max.replace(/\%|,/g, ''))
        this.totalPercentageMax += percentageValue
        const percentageValueMin = parseFloat(item.percentage.min.replace(/\%|,/g, ''))
        this.totalPercentageMin += percentageValueMin
      })
    },
    numberWithCommas(x) {
      return x.toString().replace(/\B(?=(\d{3})+(?!\d))/g, ",");
    },
    asset: window.Vapor.asset
  },
  mounted () {
    this.calcTotalOrders()
  }

}
</script>

<style scoped>
.logo-img {
  width: 75px;
  filter: grayscale(100%);
  opacity: 0.5;
}

</style>