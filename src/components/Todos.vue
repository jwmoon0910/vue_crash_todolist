<template>
  <div>
    <div v-bind:key="todo.id" v-for="todo in todos">
      <p>
        <TodoItem
          v-bind:todo="todo"
          v-on:del-todo="$emit('del-todo',todo.id)
        />
      </p>
    </div>
  </div>
</template>

<script>
import TodoItem from "./Todoitem.vue";
export default {
  name: "Todos",
  components: {
    TodoItem,
  },
  props: ["todos"],
};
</script>

<style scoped>
</style>>
