<template>
  <aside class="w-64 hidden lg:block">
    <div class="p-6">
      <nav class="space-y-4">
        <button class="flex items-center gap-3 px-3 py-2 rounded-lg bg-gray-100 w-full">🏠 Explore</button>
        <button class="flex items-center gap-3 px-3 py-2 rounded-lg w-full">👥 Following</button>
        <button class="flex items-center gap-3 px-3 py-2 rounded-lg w-full">✉️ Messages</button>
      </nav>
      <div class="mt-8">
        <button class="w-full bg-gray-900 text-white py-2 rounded">Login</button>
      </div>
    </div>
  </aside>
</template>

<script>
export default { name: 'Sidebar' }
</script>
