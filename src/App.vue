<template>
  <div id="app" class="app-container">
    <div class="todo-container bg-white rounded-lg shadow-md p-6 m-4 w-1/2 mx-auto">
      <h1 class="text-3xl font-bold text-center mb-4">Todo List</h1>
      <textarea class="w-full px-3 py-2 text-gray-700 border rounded-lg focus:outline-none" rows="4" v-model="newTodo" @keyup.enter="addTodos"></textarea>
      <button class="mt-2 w-full p-2 text-white bg-blue-600 rounded hover:bg-blue-500" @click="addTodos">Add Todos</button>
      <h2 class="text-xl font-bold mt-4">Uncompleted Todos</h2>
      <ul>
        <li class="flex justify-between items-center bg-gray-100 rounded-lg p-2 my-2" v-for="(todo, index) in todos" :key="index">
          <span class="overflow-auto whitespace-normal text-gray-800">{{ todo.text }}</span>
          <button class="text-white bg-green-500 rounded px-2 py-1 hover:bg-green-400" @click="completeTodo(index)">Complete</button>
        </li>
      </ul>
      <div class="flex justify-between items-center">
        <h2 class="text-xl font-bold mt-4">Completed Todos</h2>
        <button class="mt-2 p-2 text-white bg-blue-600 rounded hover:bg-blue-500" @click="clearCompletedTodos">Clear Completed Todos</button>
      </div>      <ul>
        <li class="flex justify-between items-center bg-gray-100 rounded-lg p-2 my-2" v-for="(todo, index) in completedTodos" :key="index">
          <span class="text-gray-800 line-through">{{ todo.text }}</span>
          <button class="text-white bg-gray-500 rounded px-2 py-1 hover:bg-gray-400" @click="uncompleteTodo(index)">Uncomplete</button>
        </li>
      </ul >

    </div>

  </div>
</template>

<script setup>
import { ref, onMounted, onBeforeUnmount } from 'vue';

const newTodo = ref("");
const todos = ref([]);
const completedTodos = ref([]);

const addTodos = () => {
  if (/^\d+\./.test(newTodo.value)) {
    const todoList = newTodo.value.split(/\d+\./).slice(1);
    todoList.forEach(todo => {
      todos.value.push({ text: todo.trim() });
    });
  } else {
    todos.value.push({ text: newTodo.value.trim() });
  }
  newTodo.value = "";
  saveTodos();
};

const completeTodo = (index) => {
  completedTodos.value.push(todos.value[index]);
  todos.value.splice(index, 1);
  saveTodos();
};
const uncompleteTodo = (index) => {
  todos.value.push(completedTodos.value[index]);
  completedTodos.value.splice(index, 1);
  saveTodos();
};
const saveTodos = () => {
  localStorage.setItem('todos', JSON.stringify(todos.value));
  localStorage.setItem('completedTodos', JSON.stringify(completedTodos.value));
};

const loadTodos = () => {
  const storedTodos = localStorage.getItem('todos');
  const storedCompletedTodos = localStorage.getItem('completedTodos');
  if (storedTodos) {
    todos.value = JSON.parse(storedTodos);
  }
  if (storedCompletedTodos) {
    completedTodos.value = JSON.parse(storedCompletedTodos);
  }
};
const clearCompletedTodos = () => {
  completedTodos.value = [];
  saveTodos();
};
onMounted(loadTodos);
onBeforeUnmount(saveTodos);
</script>

<style scoped>
.app-container {
  display: flex;
  justify-content: center;
  align-items: center;

}

.todo-container {
  /*text-align: center;*/
}
</style>
