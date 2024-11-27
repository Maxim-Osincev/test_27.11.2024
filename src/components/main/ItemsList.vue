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
  <div>
    <div
      v-for="item in items"
      :key="item.id"
      @click="$emit('item-click', item)"
    >
      {{ item.name }}
    </div>
  </div>
</template>

<style scoped>

</style>
