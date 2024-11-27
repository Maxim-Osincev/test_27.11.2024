<script>
export default {
  name: 'ItemsList',
  props: {
    items: {
      type: Array,
      default: () => []
    }
  },
  emits: ['item-click']
}
</script>

<template>
  <div class="items_list__wrapper">
    <div
      v-for="item in items"
      :key="item.id"
      class="items_list__list-item"
      @click="$emit('item-click', item)"
    >
      {{ item.name }}
    </div>
  </div>
</template>

<style scoped>
.items_list__wrapper {
  padding: 8px;
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
  border: 1px solid #000000;
}
.items_list__list-item {
  padding: 8px;
  border: 1px solid #000000;
  width: 50px;
  height: 50px;
}
</style>
