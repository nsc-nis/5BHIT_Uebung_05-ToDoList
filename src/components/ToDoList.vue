<template>
  <ul>
    <li v-for="(item, index) in toDoList" :key="index">
      <input
        type="checkbox"
        :id="item.name"
        :value="item.name"
        v-model="checkedItems"
      />
      {{ item.name }}
    </li>
  </ul>
  {{ checkedItems }}
</template>

<script>
import { ref } from "vue";
export default {
  props: {
    toDoList: {
      type: Array,
      require: true
    }
  },
  setup() {
    const checkedItems = ref([]);
    return { checkedItems };
  }
};
</script>

<style scoped>
ul {
  list-style: none;
}
</style>
