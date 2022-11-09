<template>
  <ul>
    <li v-for="(item, index) in toDoList" :key="index">
      {{ item.name }}
    </li>
  </ul>
</template>

<script>
export default {
  props: {
    toDoList: {
      type: Array,
      require: true
    }
  },
  setup() {
    return {};
  }
};
</script>

<style scoped></style>
