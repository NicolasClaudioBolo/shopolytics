<template>
    <div class="flex w-100 justify-start">
        <div class="basis-44">
            <stats1-vue/>
        </div>
        <div class="basis-44">
            <stats2-vue/>
        </div>
        <div class="basis-44">
            <stats3-vue/>
        </div>
        <div class="basis-44">
            <stats4-vue/>
        </div>
        <div class="basis-44">
            <stats1-vue/>
        </div>
        <div class="basis-44">
            <stats3-vue/>
        </div>
        <div class="basis-44">
            <stats2-vue/>
        </div>
    </div>
    <div>
        <h1 class="w-24 h-6 font-['PT Root UI'] font-bold text-sm leading-6 tracking-wider text-[#637381] mx-12 my-10">
            STORES LIST
        </h1>
        <div class="flex">
            <div class="basis-44 ml-12">
                <store-list-vue/>
            </div>
            <div class="basis-44 ml-12">
                <store-list-vue/>
            </div>
            <div class="basis-44 ml-12">
                <store-list-vue/>
            </div>
            <div class="basis 44 ml-6">
                <my-stores-vue/>
            </div>
        </div>
        <div class="flex">
            <div class="basis-44 ml-12">
                <store-list-vue/>
            </div>
            <div class="basis-44 ml-12">
                <store-list-vue/>
            </div>
            <div class="basis-44 ml-12">
                <store-list-vue/>
            </div>
        <div>
            <div class="mt-[180px] ml-6">
                <my-stores-vue/>
            </div>
        </div>
        </div>
        <div class="flex">
            <div class="basis-44 ml-12">
                <store-list-vue/>
            </div>
            <div class="basis-44 ml-12">
                <store-list-vue/>
            </div>
        </div>
    </div>

</template>


<script>
import Layout from "../Layout.vue";
import StoreListVue from "../components/multistoreoverview/StoreList.vue";
import MyStoresVue from "../components/multistoreoverview/MyStores.vue";
import OrderFeedVue from "../components/multistoreoverview/OrderFeed.vue";
import Stats1Vue from "../../../../VueHTML/VueFiles/src/components/Stats1/Stats1.vue";
import Stats2Vue from "../../../../VueHTML/VueFiles/src/components/Stats2/Stats2.vue";
import Stats3Vue from "../../../../VueHTML/VueFiles/src/components/Stats3/Stats3.vue";
import Stats4Vue from "../../../../VueHTML/VueFiles/src/components/Stats4/Stats4.vue";

export default {
    name: 'multistoreoverview',
    layout: (h, page) => (Layout, () => child),
    layout: Layout,
    components: {
        StoreListVue,
        MyStoresVue,
        OrderFeedVue,
        Stats1Vue,
        Stats2Vue,
        Stats3Vue,
        Stats4Vue
    }
}
</script>

<style></style>