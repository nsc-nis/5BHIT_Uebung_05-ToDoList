<template> </template>

<script>
import { ref } from "vue";

export default {
  setup() {
    let data = ref(
      { name: "Eating" },
      { name: "Drinking" },
      { name: "Sleeping" }
    );
    
    function createItem(item)
    {
        console.log("Create item: " + item);
        data.value.push({name: item});
    }
    
    function deleteItem(id)
    {
        console.log("Delete " + id);
    }
    return { data, createItem, deleteItem };
  }
};
</script>

<style scoped></style>
