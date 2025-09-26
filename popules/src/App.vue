<script>
import Header from './components/Header.vue'
import Sidebar from './components/Sidebar.vue'

export default {
  components: { Header, Sidebar }
}
</script>

<template>
  <div class="min-h-screen bg-white flex flex-col">
    <Header />

    <div class="flex flex-1">
      <Sidebar />

      <main class="flex-1 p-6 bg-gray-50">
        <h1 class="text-xl font-semibold">Main Content Area</h1>
      </main>
    </div>
  </div>
</template>
