<script>
import ItemsList from '@/components/main/ItemsList.vue'

const items = [
  {
    id: 1,
    name: 'Shoes 1'
  },
  {
    id: 2,
    name: 'Shoes 2'
  },
  {
    id: 3,
    name: 'Shoes 3'
  },
  {
    id: 4,
    name: 'Shoes 4'
  },
  {
    id: 5,
    name: 'T-shirt 1'
  },
  {
    id: 6,
    name: 'T-shirt 2'
  },
  {
    id: 7,
    name: 'T-shirt 3'
  },
  {
    id: 8,
    name: 'T-shirt 4'
  }
];

export default {
  name: 'UserItems',
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
      if (this.selectedItems.length >= 6) return;
      this.selectedItems.push(item);
      const itemIdx = this.getItemIndex(this.items, item);
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
      <div>Selected: {{ selectedItems.length }} / 6</div>
    </div>
    <items-list :items="items" @item-click="addSelectedItem" />
  </div>
</template>

<style scoped>
.items__selected_list {
  margin-bottom: 8px;
}
</style>
