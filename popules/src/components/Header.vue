<script setup>
import { Search, Grip, Bell, User } from 'lucide-vue-next'
</script>

<template>
  <header class="flex items-center justify-between px-6 py-6 border-b border-gray-200 bg-white sticky top-0 z-10">
    <img src="/popules_logo.png" alt="Popules Logo" class="h-11 w-auto">
    
    <!-- Search -->
    <div class="flex-1 mx-6 pl-15">
      <div class="relative">
        <div class="absolute inset-y-0 right-0 pr-3 flex items-center pointer-events-none ">
          <Search class="h-6 w-6 text-gray-400" />
        </div>
        <input 
          type="text" 
          placeholder="Search..." 
          class="block w-full pl-10 pr-3 py-2 border border-gray-100 rounded-full bg-gray-50 focus:outline-none focus:border-transparent"
        >
      </div>
    </div>

    <!-- Buttons -->
    <div class="flex items-center gap-4">
      <button class="bg-pink-500 text-white px-5 py-2 rounded-full font-bold">Post</button>
      <button class="bg-gray-200 w-10 h-10 rounded-full flex items-center justify-center">
        <Grip class="w-5 h-5" />
      </button>
      <button class="bg-gray-200 w-10 h-10 rounded-full flex items-center justify-center">
        <Bell class="w-5 h-5" />
      </button>
      <button class="bg-gray-200 w-10 h-10 rounded-full flex items-center justify-center">
        <User class="w-5 h-5" />
      </button>
    </div>
  </header>
</template>
