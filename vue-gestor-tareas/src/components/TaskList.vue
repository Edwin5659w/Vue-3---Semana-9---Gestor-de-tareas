<template>
  <div class="task-list">
    <div v-if="tasks.length === 0" class="no-tasks">
      No hay tareas registradas.
    </div>
    <div v-else class="columns">
      <TaskColumn
        title="To do"
        color="blue"
        :tasks="tasks.filter(t => t.status === 'todo')"
        :status="'todo'"
        @move-task="moveTask"
      />
      <TaskColumn
        title="Doing"
        color="green"
        :tasks="tasks.filter(t => t.status === 'doing')"
        :status="'doing'"
        @move-task="moveTask"
      />
      <TaskColumn
        title="Done"
        color="red"
        :tasks="tasks.filter(t => t.status === 'done')"
        :status="'done'"
        @move-task="moveTask"
      />
    </div>
  </div>
</template>

<script setup>
import TaskColumn from './TaskColumn.vue';
const props = defineProps(['tasks']);
const emit = defineEmits(['move-task']);

function moveTask(index, from, to) {
  emit('move-task', index, from, to);
}
</script>

<style scoped>
.task-list {
  display: flex;
  justify-content: space-between;
}

.no-tasks-message {
  text-align: center;
  color: gray;
}
</style>