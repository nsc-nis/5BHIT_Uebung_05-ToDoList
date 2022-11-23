<template>
  <div class="container">
    <Create :create="createItem" />
    <ToDoList :toDoList="data" :deleteItem="deleteItem"/>
  </div>
</template>

<script>
import { ref } from "vue";
import Create from "./Create.vue";
import ToDoList from "./ToDoList.vue";

export default {
  components: { Create, ToDoList },
  setup() {
    let data = ref([
      { name: "Eating" },
      { name: "Drinking" },
      { name: "Sleeping" }
    ]);

    function createItem(item) {
      console.log("Create item: " + item);
      data.value.push({ name: item });
    }

    function deleteItem(id) {
      console.log("Delete " + id);
      data.value.splice(id, 1)
    }
    return { data, createItem, deleteItem };
  }
};
</script>

<style scoped>
.container {
  font-size: 20px;
  display: flex;
  flex-direction: column;
  width: 60%;
  margin-left: auto;
  margin-right: auto;
}
input {
  font-size: 20px;
  border-radius: 5px;
}
button {
  border-radius: 5px;
  font-size: 20px;
  background-color: aquamarine;
}
</style>
