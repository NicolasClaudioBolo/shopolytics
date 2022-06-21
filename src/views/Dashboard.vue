<template>
  <div class="p-6 flex">
    <div class="flex flex-col w-9/12">
      <net-sales />
    </div>
    <div class="flex flex-col w-3/12">
      <financial-position/>
    </div>
  </div>
  <div class="p-6 flex">
    <div class="w-4/12 mr-4">
      <store-visitor-data/>
    </div>
    <div class="w-5/12 mr-4">
      <top-channels/>
    </div>
    <div class="w-3/12">
      <store-metrics/>
    </div>
  </div>
  <div class="p-6 flex">
    <div class="flex flex-col w-3/12 h-52 mr-4">
      <customer-data/>
    </div>
    <div class="flex flex-col w-5/12 h-52 mr-4">
      <chart/>
    </div>
    <div class="flex flex-col w-4/12 h-52">
      <top-customers/>
    </div>
  </div>
  <div class="p-6 flex">
    <div class="flex flex-col w-4/12 h-72 mr-4">
      <order-metrics/>
    </div>
    <div class="flex flex-col w-5/12 h-72 mr-4">
      <payment-methods/>
    </div>
    <div class="flex flex-col w-3/12 h-72 mr-4">
      <order-data/>
    </div>
  </div>
  <div class="p-6 flex">
    <div class="flex flex-col w-3/12 h-52 mr-4">
     <conversion-rate/>
    </div>
  </div>
</template>

<script>
import NetSales from '../components/dashbaord/NetSales.vue'
import FinancialPosition from '../components/dashbaord/FinancialPosition.vue'
import StoreVisitorData from '../components/dashbaord/StoreVisitorData.vue'
import Layout from '../Layout.vue'
import TopChannels from '../components/dashbaord/TopChannels.vue'
import StoreMetrics from '../components/dashbaord/StoreMetrics.vue'
import CustomerData from '../components/dashbaord/CustomerData.vue'
import Chart from '../components/dashbaord/Chart.vue'
import TopCustomers from '../components/dashbaord/TopCustomers.vue'
import OrderMetrics from '../components/dashbaord/OrderMetrics.vue'
import PaymentMethods from '../components/dashbaord/PaymentMethods.vue'
import OrderData from '../components/dashbaord/OrderData.vue'
import ConversionRate from '../components/dashbaord/ConversionRate.vue'

export default {
  name: 'Dashboard',
  layout: (h, page) => h(Layout, () => child),
  layout: Layout,
  components: {
    NetSales,
    FinancialPosition,
    StoreVisitorData,
    TopChannels,
    StoreMetrics,
    CustomerData,
    Chart,
    TopCustomers,
    OrderMetrics,
    PaymentMethods,
    OrderData,
    ConversionRate
  }
}
</script>

<style>

</style>
