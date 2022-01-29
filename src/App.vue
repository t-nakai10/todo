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
};
function deleteTodo(id) {
  items.forEach(function(item, index) {
    if (item.id === id) {
      items.splice(index, 1);
    }
  });
};
</script>
<template>
  <div class="container">
    <Header title="Todo List" />
    <Todos @delete-todo="deleteTodo" :todos="items" />
    <AddButton msg="追加" @add-todo="appAction" />
  </div>
</template>

<style>
.container {
  max-width: 500px;
  margin: 30px auto;

}
*,
*:before,
*:after {
  box-sizing: inherit;
}
html {
  box-sizing: border-box;
}
button {
  font-size: 1.6rem;
  font-weight: 700;
  line-height: 1.5;
  position: relative;
  display: inline-block;
  padding: 0.2rem 4rem;
  cursor: pointer;
  user-select: none;
  -webkit-transition: all 0.3s;
  transition: all 0.3s;
  text-align: center;
  vertical-align: middle;
  text-decoration: none;
  letter-spacing: 0.1em;
  color: #212529;
  border-radius: 0.5rem;
  color: #fff;
  border: none;
  border-radius: 0;
  background-image: linear-gradient(to right, #fa709a 0%, #fee140 100%);
  -webkit-box-shadow: 0 5px 10px rgba(0, 0, 0, .1);
  box-shadow: 0 5px 10px rgba(0, 0, 0, .1);
}
button:hover {
  transform: translate(0, -2px);
  color: #fff;
  box-shadow: 0 8px 15px rgba(0, 0, 0, .2);
}
input{
    width: 100%; /*親要素いっぱい広げる*/
    padding: 10px 15px; /*ボックスを大きくする*/
    font-size: 16px;
    border-radius: 3px; /*ボックス角の丸み*/
    border: 2px solid #ddd; /*枠線*/
    box-sizing: border-box; /*横幅の解釈をpadding, borderまでとする*/
}
</style>
