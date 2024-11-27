<script>
import UserItems from '@/components/main/UserItems.vue'
import AvailableItems from '@/components/main/AvailableItems.vue'

export default {
  name: 'MainView',
  components: {
    UserItems,
    AvailableItems,
  },
}
</script>

<template>
  <div>
    <user-items />
    <available-items />
  </div>
</template>

<style scoped>

</style>
