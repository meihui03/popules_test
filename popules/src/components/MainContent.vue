<script>
import { Heart } from 'lucide-vue-next'
import axios from 'axios'

export default {
  components: {
    Heart,
  },
  data() {
    return {
      items: [],
      offset: 0,
      limit: 15,
      loading: false,
      finished: false,
    }
  },
  mounted() {
    this.fetchDataFromAPI()
    window.addEventListener('scroll', this.handleScroll)
  },
  beforeUnmount() {
    window.removeEventListener('scroll', this.handleScroll)
  },
  methods: {
    fetchDataFromAPI() {
      if (this.loading || this.finished) return

      this.loading = true
      axios
        .get(`https://api.popules.com/api/feed?offset=${this.offset}&limit=${this.limit}`)
        .then((response) => {
          const newData = response.data.data.map(post => ({
            id: post.id,
            title: post.title,
            image: post.uploads[0] || '',
            user: post.user.fullname,
            profile: post.user.logo_url || '',
            likes_count: post.likes_count || 0,
          }))

          if (newData.length === 0) {
            this.finished = true
          } else {
            this.items.push(...newData)
            this.offset += this.limit
          }
        })
        .catch((error) => {
          console.error('Error fetching', error)
        })
        .finally(() => {
          this.loading = false
        })
    },
    handleScroll() {
      const scrollPosition = window.innerHeight + window.scrollY
      const threshold = document.body.offsetHeight - 200
      if (scrollPosition >= threshold) {
        this.fetchDataFromAPI()
      }
    },
  },
}
</script>

<template>
  <div class="columns-1 sm:columns-2 md:columns-3 lg:columns-4 xl:columns-5 gap-4">
    <div
      v-for="item in items"
      :key="item.id"
      class="bg-white rounded-xl shadow hover:shadow-lg transition overflow-hidden mb-4 break-inside-avoid"
    >
      <img
        :src="item.image"
        :alt="item.title"
        class="w-full h-auto object-cover"
      />
      <div class="p-3 flex flex-col gap-2">
        <h3 class="text-sm font-semibold text-gray-800 mb-2 line-clamp-2">
          {{ item.title }}
        </h3>
        <div class="flex items-center justify-between mt-auto">
          <div class="flex items-center gap-2">
            <img 
              :src="item.profile" 
              alt="profile" 
              class="rounded-full w-6 h-6 object-cover bg-gray-200" 
            />
            <p class="text-xs text-gray-600 truncate">by {{ item.user }}</p>
          </div>
          <div class="flex items-center gap-1 flex-shrink-0">
            <Heart class="w-4 h-4 text-gray-600 cursor-pointer hover:text-red-500 transition" />
            <span class="text-xs text-gray-600">{{ item.likes_count }}</span>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

