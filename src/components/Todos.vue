<script setup>
  const props = defineProps({
    todos: Array,
  })
</script>

<template>
  <div v-for="todo in todos" v-bind:key="todo.id" class="todos">
    <h3>
      {{ todo.todoName }}
    </h3>
    <p>{{ todo.cleatedAt }}</p>
  </div>
</template>

<style scoped>
  .todos {
    box-shadow: 0 10px 25px 0 rgba(0,0,0,0.1);
    min-width: 400px;
    margin: 10px auto;
    overflow: auto;
    height: auto;
    padding: 10px 20px;
  }
</style>