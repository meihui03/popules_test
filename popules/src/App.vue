<script>
import Header from './components/Header.vue'
import Sidebar from './components/Sidebar.vue'
import CategoryTabs from './components/CategoryTabs.vue';
import MainContent from './components/MainContent.vue';

export default {
  components: { Header, Sidebar ,CategoryTabs , MainContent}
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
          <MainContent/>
        </main>
      </div>
    </div>
  </div>
</template>