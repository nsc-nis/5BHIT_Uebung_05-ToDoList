<template>
  <h1>ToDo List</h1>
  <form @submit.prevent="doCreate">
    <div class="create">
      <input type="text" v-model="item" placeholder="Add ToDo Item" />
      <button>Create</button>
    </div>
  </form>
</template>

<script>
import { ref } from 'vue';

export default {
  props: {
    create: { type: Function, required: true },
  },
  setup(props) {
    let item = ref('');

    function doCreate() {
      console.log('Create...' + item.value);
      props.create(item.value);
    }
    return { item, doCreate };
  },
};
</script>

<style scoped>
input[type='text'] {
  padding: 5px;
  margin-right: 15px;
  color: #5c5c5c;
  border: 1px solid #dcdce6;
  border-radius: 8px;
}

.create {
  display: flex;
  width: 60%;
  justify-content: space-between;
  margin-bottom: 20px;
}

h1 {
  text-align: center;
}
</style>
