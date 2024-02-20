<template>
  <div>
    <!-- สร้างช่องข้อความ -->
    <input type="password" v-model="password" class="border px-4 py-2 rounded focus:outline-none focus:border-blue-500" :class="{ 'pr-10': showPassword }" placeholder="Enter password">
    
    <!-- ปุ่มเปิด/ปิด การแสดงรหัสผ่าน -->
    <button @click="toggleShowPassword" class="absolute inset-y-0 right-0 flex items-center px-2 text-gray-700">
      <svg v-if="showPassword" xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19.071 4.929A10 10 0 1 0 4.929 19.071 10 10 0 0 0 19.071 4.929zM12 15l-2-2m0 0l-2-2m2 2l2-2m-2 2l2-2m7.071-7.071a8 8 0 1 1-11.314 0 8 8 0 0 1 11.314 0z" />
      </svg>
      <svg v-else xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 12a3 3 0 1 1-6 0 3 3 0 0 1 6 0zm0 0h-2m-4 0H7m4 0a1 1 0 1 0 0-2 1 1 0 0 0 0 2zM4 12a8 8 0 0 1 16 0v4a4 4 0 0 1-4 4H8a4 4 0 0 1-4-4v-4zm0 0a8 8 0 0 1 16 0v4a4 4 0 0 1-4 4H8a4 4 0 0 1-4-4v-4zm0 0a8 8 0 0 0-4 6.928M20 12h.01M20 12a8 8 0 0 1-4 6.928" />
      </svg>
    </button>
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
