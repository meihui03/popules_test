<script setup>
import { House, Send, User, Building, ArrowDown, UserPlus, Menu } from 'lucide-vue-next'
import { ref } from 'vue'

const showMore = ref(false)
const toggleMore = () => {
  showMore.value = !showMore.value
}
</script>

<template>
  <aside class="w-64 bg-white h-[90vh] border-r border-gray-200 sticky top-0">
    <div class="p-5 flex flex-col h-full">
      
      <!-- Top section -->
      <div>
        <!-- Navigation Links -->
        <nav class="space-y-2">
          <a href="#" class="flex items-center px-4 py-3 text-gray-800 rounded-full hover:bg-gray-100 font-medium">
            <House class="h-6 w-6 text-gray-600 mr-3" />
            Explore
          </a>
          
          <a href="#" class="flex items-center px-4 py-3 text-gray-800 rounded-full hover:bg-gray-100 font-medium">
            <UserPlus class="h-6 w-6 text-gray-600 mr-3" />
            Following
          </a>
          
          <a href="#" class="flex items-center px-4 py-3 text-gray-800 rounded-full hover:bg-gray-100 font-medium">
            <Send class="h-5 w-5 text-gray-600 mr-3" />
            Messages
          </a>

          <button 
            v-if="!showMore"
            @click="toggleMore" 
            class="flex items-center px-4 py-3 text-gray-800 rounded-full hover:bg-gray-100 font-medium w-full"
          >
            <ArrowDown class="h-6 w-6 text-gray-600 mr-3" />
            More
          </button>

          <template v-if="showMore">
            <a href="#" class="flex items-center px-4 py-3 text-gray-800 rounded-full hover:bg-gray-100 font-medium">
              <User class="h-6 w-6 text-gray-600 mr-3" />
              Profile
            </a>
            <a href="#" class="flex items-center px-4 py-3 text-gray-800 rounded-full hover:bg-gray-100 font-medium">
              <Building class="h-6 w-6 text-gray-600 mr-3" />
              Business
            </a>

            <button 
              @click="toggleMore" 
              class="flex items-center px-4 py-3 text-gray-800 rounded-full hover:bg-gray-100 font-medium w-full"
            >
              <ArrowDown class="h-6 w-6 text-gray-600 mr-3 transform rotate-180" />
              Less
            </button>
          </template>
        </nav>

        <!-- Divider line -->
        <hr class="my-4 border-t border-gray-200" />

        <!-- Community Section -->
        <div>
          <p class="text-lg text-gray-600 mb-3">Join our community now!</p>
          <button
            class="w-full bg-gray-700 text-white py-2 px-4 rounded-full hover:bg-white hover:text-black border border-transparent hover:border-gray-400 transition duration-200"
          >
            Login
          </button>
        </div>
      </div>
      <a href="#" class="mt-auto flex items-center px-4 py-3 text-gray-800 rounded-full hover:bg-gray-100 font-medium">
        <Menu class="h-6 w-6 text-gray-600 mr-3" />
        More
      </a>
    </div>
  </aside>
</template>
