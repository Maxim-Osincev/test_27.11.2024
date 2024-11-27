<script>
import ItemsList from '@/components/main/ItemsList.vue'

const items = [
  {
    "id": 11,
    "name": "Jacket 1"
  },
  {
    "id": 12,
    "name": "Jacket 2"
  },
  {
    "id": 13,
    "name": "Jacket 3"
  },
  {
    "id": 14,
    "name": "Jacket 4"
  },
  {
    "id": 15,
    "name": "Hoodie 1"
  },
  {
    "id": 16,
    "name": "Hoodie 2"
  },
  {
    "id": 17,
    "name": "Hoodie 3"
  },
  {
    "id": 18,
    "name": "Hoodie 4"
  }
];

export default {
  name: 'AvailableItems',
  data () {
    return {
      items,
      selectedItems: []
    }
  },
  components: {
    ItemsList
  },
  methods: {
    addSelectedItem (item) {
      if (this.selectedItems.length) return;
      this.selectedItems.push(item);
      const itemIdx = this.items.indexOf(item);
      this.items.splice(itemIdx, 1);
    },
    removeSelectedItem (item) {
      this.items.push(item);
      const itemIdx = this.getItemIndex(this.selectedItems, item);
      this.selectedItems.splice(itemIdx, 1);
    },
    getItemIndex (list, target) {
      return list.indexOf(target);
    },
  }
}
</script>

<template>
  <div>
    <div class="items__selected">
      <div v-if="selectedItems.length" class="items__selected_list">
        <div
            v-for="item in selectedItems"
            :key="item.id"
            class="items__selected-item"
            @click="removeSelectedItem(item)"
        >
          {{ item.name }}
        </div>
      </div>
    </div>
    <items-list :items="items" @item-click="addSelectedItem" />
  </div>
</template>

<style scoped>
</style>
