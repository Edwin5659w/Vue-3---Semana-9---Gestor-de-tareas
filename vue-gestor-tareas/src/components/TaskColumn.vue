<template>
  <div class="task-column" :class="color">
    <h3>{{ title }}</h3>
    <div v-for="(task, idx) in tasks" :key="idx" class="task-card">
      <span>{{ task.name }}</span>
      <div v-if="status !== 'done'" class="actions">
        <button
          v-if="status === 'todo'"
          @click="$emit('move-task', idx, 'todo', 'doing')"
          class="move-btn"
        >
          ➡️
        </button>
        <button
          v-if="status === 'doing'"
          @click="$emit('move-task', idx, 'doing', 'done')"
          class="move-btn"
        >
          ➡️
        </button>
      </div>
    </div>
  </div>
</template>

<script setup>
const props = defineProps(['title', 'color', 'tasks', 'status']);
</script>

<style scoped>
.task-column {
  border: 1px solid #ccc;
  border-radius: 5px;
  padding: 10px;
  margin: 10px;
  background-color: #f9f9f9;
}

.task-column h2 {
  color: #333;
}

.task-column ul {
  list-style-type: none;
  padding: 0;
}

.task-column li {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 5px 0;
}

.task-column button {
  margin-left: 5px;
  cursor: pointer;
}

.task-card {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 10px;
  border: 1px solid #ddd;
  border-radius: 3px;
  margin-bottom: 10px;
  background-color: #fff;
}

.actions {
  display: flex;
}

.move-btn {
  margin-left: 5px;
  cursor: pointer;
}
</style>