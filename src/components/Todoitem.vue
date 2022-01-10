<template>
  <div class="todo-item" v-bind:class="{ 'is-complete': todo.completed }">
    <p>
      <input type="checkbox" v-on:change="markComplete" />
      {{ todo.title }}
      <button @click="$emit('del-todo', todo.id)" class="del">x</button>
    </p>
  </div>
</template>

<script>
export default {
  name: "TodoItem",
  props: ["todo"],
  methods: {
    markcompleted() {
      this.todo.completed = !this.todo.completed;
    },
  },
};
</script>

<style scoped>
.todo-item {
  background: greenyellow;
  padding: 10;
  border-bottom: 1px #ccc dotted;
}
.is-complete {
  text-decoration: line-through;
}
.del {
  background: #f00;
  color: #f4f4f4;
  border: none;
  padding: 5px 9px;
  border-radius: 50%;
  float: right;
}
</style>