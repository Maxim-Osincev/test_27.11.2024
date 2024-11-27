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
  <div class="main__wrapper">
    <user-items class="main__col" />
    <available-items class="main__col" />
  </div>
</template>

<style>
.main__wrapper {
  display: flex;
  flex-wrap: nowrap;
  gap: 16px;
  justify-content: space-between;
}
.main__col {
  flex: 0 1 50%;
}
.items__selected {
  border: 1px solid #000000;
  padding: 8px;
  margin-bottom: 16px;
  min-height: 30px;
}
.items__selected_list {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
  margin-bottom: 8px;
}
.items__selected-item {
  padding: 8px;
  border: 1px solid #000000;
  width: 50px;
  height: 50px;
}
</style>
