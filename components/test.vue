<template>
  <div>
    <!-- ช่องใส่รหัสผ่าน -->
    <div class="relative">
      <input type="password" v-model="password" class="border px-4 py-2 rounded focus:outline-none focus:border-blue-500" :class="{ 'pr-10': showPassword }" placeholder="Enter password">
      <!-- ปุ่มเปิด/ปิด การแสดงรหัสผ่าน -->
      <button @click="toggleShowPassword" class="absolute inset-y-0 right-0 flex items-center px-2 text-gray-700">
        <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" :class="{ 'text-blue-500': showPassword, 'text-gray-500': !showPassword }">
          <path v-if="showPassword" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 9a2 2 0 0 1 2-2h8a2 2 0 0 1 2 2v6a2 2 0 0 1-2 2H8a2 2 0 0 1-2-2V9z"/>
          <path v-else stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 12a3 3 0 1 1-6 0 3 3 0 0 1 6 0zm-3 0a1 1 0 1 0-2 0 1 1 0 0 0 2 0z"/>
        </svg>
      </button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      password: '',
      showPassword: false
    };
  },
  methods: {
    toggleShowPassword() {
      this.showPassword = !this.showPassword;
    }
  }
};
</script>
