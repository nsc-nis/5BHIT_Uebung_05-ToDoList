<template>
  <ul>
    <li v-for="(item, index) in toDoList" :key="index">
      <input
        type="checkbox"
        :id="item.name"
        :value="item.name"
        v-model="checkedItems"
      />
      <span :class="{ done: checkedItems.includes(item.name) }">{{
        item.name
      }}</span>

      <span class="delete" @click="deleteItem(index)">X</span>
    </li>
  </ul>
</template>

<script>
import { ref } from 'vue';
export default {
  props: {
    deleteItem: {
      type: Function,
      required: true,
    },
    toDoList: {
      type: Array,
      require: true,
    },
  },
  setup() {
    const checkedItems = ref([]);
    return { checkedItems };
  },
};
</script>

<style scoped>
ul {
  list-style: none;
  flex-direction: column;
  width: 25%;
  margin: auto;
  font-family: 'Lato', sans-serif;
  font-size: 20px;
  font-weight: 400;
  font-style: italic;
}
ul li {
  margin-bottom: 10px;
  color: #5c5c5c;
  display: flex;
  margin: 5px 0;
  justify-content: space-between;
  align-content: center;
}
ul li :hover {
  opacity: 0.4;
}
.delete {
  background-color: red;
  color: white;
  padding: 0 10px;
  line-height: 1;
  border-radius: 5px;
  cursor: pointer;
}
.hideDelete {
  opacity: 0;
}

.done {
  text-decoration: line-through;
}
.taskInfo {
  margin-top: 15px;
  font-size: 14px;
  display: flex;
  margin-left: auto;
  color: #335c62;
  justify-self: space-between;
}
.doneTasks {
  position: absolute;
  left: 20px;
}
input[type='checkbox'] {
  width: 20px;
  background: #555;
  border-radius: 5px;
}
</style>
