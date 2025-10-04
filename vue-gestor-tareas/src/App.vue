<template>
  <div class="app-container">
    <h1>Gestor de tareas</h1>
    <TaskInput @add-task="addTask" />
    <h2 class="list-title">Listado de tareas</h2>
    <TaskList
      :tasks="tasks"
      @move-task="moveTask"
    />
  </div>
</template>

<script setup>
import { ref } from 'vue';
import TaskInput from './components/TaskInput.vue';
import TaskList from './components/TaskList.vue';

const tasks = ref([]);

function addTask(name) {
  if (name.trim()) {
    tasks.value.push({ name, status: 'todo' });
  }
}

function moveTask(index, from, to) {
  const taskIndex = tasks.value.findIndex(
    (t, i) => i === index && t.status === from
  );
  if (taskIndex !== -1) {
    tasks.value[taskIndex].status = to;
  }
}
</script>

<style src="./styles/custom.css"></style>