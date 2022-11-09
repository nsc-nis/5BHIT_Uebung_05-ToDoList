<template>
  <form>
    <input type="text" v-model="item" placeholder="Add ToDo Item" />
    <button>Create</button>
  </form>
</template>

<script>
import { ref } from "vue";

export default {
  setup() {
    let item = ref("");
    return { item };
  }
};
</script>

<style scoped></style>
