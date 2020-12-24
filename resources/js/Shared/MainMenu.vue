<template>
  <div>
    <div class="mb-4">
      <inertia-link class="flex items-center group py-3" :href="route('dashboard')">
        <icon name="dashboard" class="w-4 h-4 mr-2" :class="isUrl('') ? 'fill-blue-500' : 'fill-blue-500 group-hover:fill-white'" />
        <div :class="isUrl('') ? 'text-white' : 'text-blue-500 group-hover:text-blue-700'">Dashboard</div>
      </inertia-link>
    </div>
    <div class="mb-4">
      <inertia-link class="flex items-center group py-3" :href="route('organizations')">
        <icon name="office" class="w-4 h-4 mr-2" :class="isUrl('organizations') ? 'fill-blue-500' : 'fill-blue-500 group-hover:fill-white'" />
        <div :class="isUrl('organizations') ? 'text-white' : 'text-blue-500 group-hover:text-blue-700'">Organizations</div>
      </inertia-link>
    </div>
    <div class="mb-4">
      <inertia-link class="flex items-center group py-3" :href="route('contacts')">
        <icon name="users" class="w-4 h-4 mr-2" :class="isUrl('contacts') ? 'fill-blue-500' : 'fill-blue-500 group-hover:fill-white'" />
        <div :class="isUrl('contacts') ? 'text-white' : 'text-blue-500 group-hover:text-blue-700'">Contacts</div>
      </inertia-link>
    </div>
    <div class="mb-4">
      <inertia-link class="flex items-center group py-3" :href="route('reports')">
        <icon name="printer" class="w-4 h-4 mr-2" :class="isUrl('reports') ? 'fill-blue-500' : 'fill-blue-500 group-hover:fill-white'" />
        <div :class="isUrl('reports') ? 'text-white' : 'text-blue-500 group-hover:text-blue-700'">Reports</div>
      </inertia-link>
    </div>
  </div>
</template>

<script>
import Icon from '@/Shared/Icon'

export default {
  components: {
    Icon,
  },
  props: {
    url: String,
  },
  methods: {
    isUrl(...urls) {
      if (urls[0] === '') {
        return this.url === ''
      }

      return urls.filter(url => this.url.startsWith(url)).length
    },
  },
}
</script>
