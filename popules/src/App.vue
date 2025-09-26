<script>
import Header from './components/Header.vue'
import Sidebar from './components/Sidebar.vue'
import CategoryTabs from './components/CategoryTabs.vue';

export default {
  components: { Header, Sidebar ,CategoryTabs }
}
</script>

<template>
  <div class="min-h-screen bg-white flex flex-col">
    <Header />
    <div class="flex flex-1">
      <Sidebar />
      <div class="flex-1 flex flex-col">
        <CategoryTabs />
        <main class="flex-1 p-6 ">
          <h1 class="text-xl font-semibold">Main Content Area</h1>
        </main>
      </div>
    </div>
  </div>
</template>