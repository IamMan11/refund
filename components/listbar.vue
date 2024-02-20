<template>
  <div class="relative">
    <!-- สร้างช่องข้อความ -->
    <input type="text" v-model="selectedItem" @click="toggleList" class="border px-4 py-2 rounded focus:outline-none focus:border-blue-500" placeholder="Select an item">

    <!-- แสดง list เมื่อถูกกด หรือมีสไลด์เมื่อมากกว่า 3 รายการ -->
    <ul v-show="isListOpen || isSliding" class="absolute z-10 mt-1 w-40 bg-white rounded-md shadow-lg overflow-y-auto max-h-40 transition" @transitionend="handleTransitionEnd">
      <li v-for="item in items" :key="item.id" @click="selectItem(item)" class="py-1 px-3 cursor-pointer hover:bg-gray-100">{{ item.name }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      selectedItem: '',
      isListOpen: false,
      isSliding: false,
      items: [
        { id: 1, name: 'Item 1' },
        { id: 2, name: 'Item 2' },
        { id: 3, name: 'Item 3' },
        { id: 3, name: 'Item 3' },
        { id: 3, name: 'Item 3' },
        { id: 3, name: 'Item 3' },
        { id: 3, name: 'Item 3' },
        // เพิ่มรายการต่อไปตามความต้องการ
      ]
    };
  },
  methods: {
    toggleList() {
      this.isListOpen = !this.isListOpen;
      if (this.items.length > 3) {
        this.isSliding = !this.isSliding;
      }
    },
    selectItem(item) {
      this.selectedItem = item.name;
      this.isListOpen = false;
      this.isSliding = false;
    },
    handleTransitionEnd() {
      if (!this.isListOpen && this.isSliding) {
        this.isSliding = false;
      }
    }
  }
};
</script>
