<!-- filepath: c:\Universidad\Tarea DW\vue-gestor-tareas\src\components\TaskInput.vue -->
<template>
  <div class="task-input">
    <input
      v-model="taskName"
      @keyup.enter="submitTask"
      placeholder="Escribe el nombre de la tarea"
      class="input"
    />
    <button @click="submitTask" class="add-btn">Agregar</button>
  </div>
</template>

<script setup>
import { ref } from 'vue';
const emit = defineEmits(['add-task']);
const taskName = ref('');

function submitTask() {
  if (taskName.value.trim()) {
    emit('add-task', taskName.value);
    taskName.value = '';
  }
}
</script>