<template>
  <div class="w-20 h-100 border flex flex-col items-center justify-between bg-white relative">
    <div class="w-full flex flex-col items-center">
      <div class="bg-gray-500 w-7 h-7 rounded-md mt-4 mb-14 cursor-pointer hover:rotate-12" :class="{'rotate-12': toggleSubMenu}" @click="toggle(false)"/>
      <div 
        v-for="item in items"
        :key="item"
        class="h-12 flex items-center w-full justify-center"
        :class="{
          'absolute hidden': item.isSubItem && (item.parent && !subItems.includes(item.parent)),
        'bg-gray-100':  selectedItem[item.name],
        'bg-gray-200':  selectedItem[item.name] && item.isSubItem
        }"
        @mouseover="selectedItem[item.name] = true"
        @mouseleave="selectedItem[item.name] = false"
      >
          <div class="flex items-center justify-center cursor-pointer relative">
            <div v-if="!item.isSubItem || (item.parent && subItems.includes(item.parent))" @click="toggle(item.name, item.isSubItem)" class="z-10">
              <img :src="asset(`images/${item.icon}.svg`)" alt="" srcset="" :class="{'selected-icon': item.name === selected, 'vector-width': item.icon === 'vector', 'graph-width': item.icon === 'graph'}">
            </div>
            <div v-if="item.name === selected" class="absolute selected-circle"/>
          </div>
      </div>
    </div>
    <div class="w-full">
      <div 
        v-for="item in supportItems"
        :key="item"
        class="h-12 flex items-center w-full justify-center"
        :class="{
          'absolute hidden': item.isSubItem && (item.parent && !subItems.includes(item.parent)),
        'bg-gray-100':  selectedItem[item.name],
        'bg-gray-200':  selectedItem[item.name] && item.isSubItem
        }"
        @mouseover="selectedItem[item.name] = true"
        @mouseleave="selectedItem[item.name] = false"
      >
          <div class="flex items-center justify-center cursor-pointer relative">
            <div v-if="!item.isSubItem || (item.parent && subItems.includes(item.parent))" @click="toggle(item.name, item.isSubItem)" class="z-10">
              <img :src="asset(`images/${item.icon}.svg`)" alt="" srcset="" :class="{'selected-icon': item.name === selected, 'vector-width': item.icon === 'vector', 'graph-width': item.icon === 'graph'}">
            </div>
            <div v-if="item.name === selected" class="absolute selected-circle"/>
          </div>
      </div>
    </div>
    <div class="h-100 w-48 flex flex-col items-center absolute submenu" v-if="toggleSubMenu">
      <div class="w-7 h-7 bg-transparent rounded-md mt-4 mb-14" />
      <div class="h-full w-full bg-white border border-l-0 shadow-sm">
        <div 
          v-for="item in items"
          :key="item"
          class="h-12 flex items-center justify-between"
          :class="{
            'absolute': item.isSubItem && (item.parent && !subItems.includes(item.parent)),
            'bg-gray-100':  selectedItem[item.name],
            'bg-gray-200':  selectedItem[item.name] && item.isSubItem
          }"
          @mouseover="selectedItem[item.name] = true"
          @mouseleave="selectedItem[item.name] = false"
        >
          <div 
            class="ml-2 text-gray-500 text-sm cursor-pointer" 
            v-if="!item.isSubItem || (item.parent && subItems.includes(item.parent))"
            :class="{
              'text-black text-xs ml-6': item.parent && subItems.includes(item.parent),
              'text-black': item.name === selected
            }"
            @click="toggle(item.name, item.isSubItem)"
          >
            {{item.name}}
          </div>
          <img :src="asset(`images/chevron-down.svg`)" class="mr-2 cursor-pointer" alt="" srcset="" v-if="item.hasChildren && subItems.indexOf(item.name) === -1" @click="showSubItems(item.name)">
          <img :src="asset(`images/chevron-up.svg`)" class="mr-2 cursor-pointer" alt="" srcset="" v-if="item.hasChildren && subItems.indexOf(item.name) !== -1" @click="showSubItems(item.name)">
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// export default {
//   name: 'Navbar',
//   data () {
//     return {
//       items: [
//         {
//           name: 'Multistore Overview',
//           icon: 'multistore'
//         },
//         {
//           name: 'Dashboard',
//           icon: 'vector'
//         },
//         {
//           name: 'Web Traffic Data',
//           icon: 'graph',
//           hasChildren: true
//         },
//         {
//           name: 'Marketing Performance',
//           icon: 'marketing-performance',
//           isSubItem: true,
//           parent: 'Web Traffic Data'
//         },
//         {
//           name: 'Segmented Analytics',
//           icon: 'segmented-analytics',
//           isSubItem: true,
//           parent: 'Web Traffic Data'
//         },
//         {
//           name: 'Web Visitor Data',
//           icon: 'visitor-data',
//           isSubItem: true,
//           parent: 'Web Traffic Data'
//         },
//         {
//           name: 'Marketing ROI',
//           icon: 'money',
//           hasChildren: true
//         },
//         {
//           name: 'eCRM',
//           icon: 'crm',
//           hasChildren: true
//         },
//         {
//           name: 'Store Data',
//           icon: 'store-data',
//           hasChildren: true
//         },
//         {
//           name: 'Cost Driver Builder',
//           icon: 'cost-driver-builder',
//           hasChildren: true
//         },
//       ],
//       supportItems: [
//         {
//           name: 'Settings',
//           icon: 'settings'
//         },
//         {
//           name: 'Support',
//           icon: 'support'
//         }
//       ],
//       toggleSubMenu: false,
//       subItems: [],
//       selectedItem: {},
//       selected: ''
//     }
//   },
//   methods: {
//     showSubItems (name) {
//       const index = this.subItems.indexOf(name)
//       if (index === -1) {
//         this.subItems = []
//         this.subItems.push(name)
//       } else {
//         this.subItems = []
//       }
//     },
//     toggle (name, isSubItem) {
//       const index = this.items.findIndex((item) => item.parent === name)
//       if (index !== -1 && this.items[index].name === this.selected) return
//       if (name === this.selected || !name) this.toggleSubMenu = !this.toggleSubMenu
//       else { this.toggleSubMenu = true }
//       if (name) this.selected = name
//       if (!isSubItem) this.showSubItems(name)
//     },
//     asset: window.Vapor.asset
//   }
// }
</script>

<style scoped>
.submenu {
  left: 76px;
  top: 3px;
  height: 100vh;
}
.selected-circle {
  background-color: #637381;
  width: 40px;
  height: 40px;
  border-radius: 99999px;
}
.selected-icon {
  margin-left: 1px;
  filter: brightness(0) invert(1);
}
.vector-width {
  width: 21px;
}
.graph-width {
  width: 26px;
}
</style>