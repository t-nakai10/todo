<script setup>
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup
import Header from './components/Header.vue';
import Todos from './components/Todos.vue';
import AddButton from './components/AddButton.vue';
import { reactive } from "@vue/reactivity"

const items = reactive([
  {
    id: 0,
    todoName: "勉強する",
    cleatedAt: "2021年9月29日",
    cleared: false,
  },
  {
    id: 1,
    todoName: "遊ぶ",
    cleatedAt: "2021年9月29日",
    cleared: false,
  },
]);
function appAction(newTodo) {
  items.push(newTodo);
}
</script>
<template>
  <div class="container">
    <Header title="Todo List" />
    <Todos :todos="items" />
    <AddButton msg="追加" @add-todo="appAction" />
  </div>
</template>

<style>
.container {
  max-width: 500px;
  margin: 30px auto;

}
</style>
