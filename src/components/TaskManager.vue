<script setup lang="ts">
import { ref, computed, onMounted } from 'vue'

interface Task {
  id: string
  title: string
  completed: boolean
  createdAt: Date
}

// State
const todos = ref<Task[]>([])
const newTaskInput = ref('')

// Computed
const completedCount = computed(() => todos.value.filter(t => t.completed).length)
const totalCount = computed(() => todos.value.length)

// Methods
const addTask = () => {
  if (newTaskInput.value.trim()) {
    todos.value.push({
      id: Date.now().toString(),
      title: newTaskInput.value,
      completed: false,
      createdAt: new Date()
    })
    newTaskInput.value = ''
    saveTasks()
  }
}

const deleteTask = (id: string) => {
  todos.value = todos.value.filter(t => t.id !== id)
  saveTasks()
}

const toggleTask = (id: string) => {
  const task = todos.value.find(t => t.id === id)
  if (task) {
    task.completed = !task.completed
    saveTasks()
  }
}

const saveTasks = () => {
  localStorage.setItem('tasks', JSON.stringify(todos.value))
}

const loadTasks = () => {
  const saved = localStorage.getItem('tasks')
  if (saved) {
    todos.value = JSON.parse(saved).map((t: Task) => ({
      ...t,
      createdAt: new Date(t.createdAt)
    }))
  }
}

// Lifecycle
onMounted(() => {
  loadTasks()
})

// Handle Enter key
const handleKeyPress = (event: KeyboardEvent) => {
  if (event.key === 'Enter') {
    addTask()
  }
}
</script>

<template>
  <div class="task-manager">
    <div class="container">
      <!-- Header -->
      <div class="header">
        <h1>📝 任务管理器</h1>
        <p class="subtitle">管理你的日常任务，提高效率</p>
      </div>

      <!-- Stats -->
      <div class="stats">
        <div class="stat-card">
          <span class="stat-label">已完成</span>
          <span class="stat-value">{{ completedCount }}</span>
        </div>
        <div class="stat-divider">/</div>
        <div class="stat-card">
          <span class="stat-label">总计</span>
          <span class="stat-value">{{ totalCount }}</span>
        </div>
      </div>

      <!-- Input Section -->
      <div class="input-section">
        <input
          v-model="newTaskInput"
          @keypress="handleKeyPress"
          type="text"
          placeholder="输入新任务并按 Enter..."
          class="task-input"
          aria-label="新任务输入框"
        />
        <button @click="addTask" class="btn btn-add" aria-label="添加任务">
          ➕ 添加
        </button>
      </div>

      <!-- Task List -->
      <div class="task-list">
        <div v-if="todos.length === 0" class="empty-state">
          <p class="empty-icon">🎯</p>
          <p class="empty-text">还没有任务，开始添加一个吧！</p>
        </div>
        <div v-else class="tasks">
          <div
            v-for="task in todos"
            :key="task.id"
            class="task-item"
            :class="{ completed: task.completed }"
          >
            <input
              type="checkbox"
              :checked="task.completed"
              @change="toggleTask(task.id)"
              class="task-checkbox"
              :aria-label="`标记 ${task.title} 为 ${task.completed ? '未完成' : '已完成'}`"
            />
            <span class="task-title">{{ task.title }}</span>
            <button
              @click="deleteTask(task.id)"
              class="btn btn-delete"
              :aria-label="`删除 ${task.title}`"
            >
              🗑️
            </button>
          </div>
        </div>
      </div>

      <!-- Progress Bar -->
      <div v-if="totalCount > 0" class="progress-section">
        <div class="progress-bar">
          <div class="progress-fill" :style="{ width: `${(completedCount / totalCount) * 100}%` }"></div>
        </div>
        <p class="progress-text">
          完成进度：{{ Math.round((completedCount / totalCount) * 100) }}%
        </p>
      </div>
    </div>
  </div>
</template>

<style scoped>
.task-manager {
  min-height: 100vh;
  padding: 2rem 1rem;
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
}

.container {
  max-width: 600px;
  margin: 0 auto;
}

.header {
  text-align: center;
  color: white;
  margin-bottom: 2rem;
}

.header h1 {
  font-size: 2.5rem;
  margin: 0 0 0.5rem 0;
  font-weight: 700;
}

.subtitle {
  font-size: 1rem;
  opacity: 0.9;
  margin: 0;
}

.stats {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 1rem;
  margin-bottom: 2rem;
  background: rgba(255, 255, 255, 0.1);
  padding: 1.5rem;
  border-radius: 12px;
  backdrop-filter: blur(10px);
}

.stat-card {
  display: flex;
  flex-direction: column;
  align-items: center;
  color: white;
}

.stat-label {
  font-size: 0.875rem;
  opacity: 0.8;
  margin-bottom: 0.25rem;
}

.stat-value {
  font-size: 2rem;
  font-weight: 700;
}

.stat-divider {
  color: white;
  opacity: 0.5;
  font-size: 1.5rem;
}

.input-section {
  display: flex;
  gap: 0.5rem;
  margin-bottom: 2rem;
}

.task-input {
  flex: 1;
  padding: 1rem;
  border: none;
  border-radius: 8px;
  font-size: 1rem;
  background: white;
  color: #333;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  transition: box-shadow 0.3s ease;
}

.task-input:focus {
  outline: none;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.2);
}

.btn {
  padding: 1rem 1.5rem;
  border: none;
  border-radius: 8px;
  font-size: 1rem;
  cursor: pointer;
  font-weight: 600;
  transition: all 0.3s ease;
}

.btn-add {
  background: white;
  color: #667eea;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}

.btn-add:hover {
  transform: translateY(-2px);
  box-shadow: 0 6px 12px rgba(0, 0, 0, 0.15);
}

.task-list {
  margin-bottom: 2rem;
}

.empty-state {
  text-align: center;
  padding: 3rem 1rem;
  background: rgba(255, 255, 255, 0.1);
  border-radius: 12px;
  color: white;
}

.empty-icon {
  font-size: 3rem;
  margin: 0 0 1rem 0;
}

.empty-text {
  margin: 0;
  opacity: 0.9;
  font-size: 1.1rem;
}

.tasks {
  display: flex;
  flex-direction: column;
  gap: 0.75rem;
}

.task-item {
  display: flex;
  align-items: center;
  gap: 0.75rem;
  padding: 1rem;
  background: white;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  transition: all 0.3s ease;
}

.task-item:hover {
  transform: translateX(4px);
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.15);
}

.task-item.completed {
  opacity: 0.6;
  background: #f5f5f5;
}

.task-checkbox {
  width: 1.25rem;
  height: 1.25rem;
  cursor: pointer;
  accent-color: #667eea;
}

.task-title {
  flex: 1;
  color: #333;
  font-size: 1rem;
  word-break: break-word;
}

.task-item.completed .task-title {
  text-decoration: line-through;
  color: #999;
}

.btn-delete {
  background: #ff6b6b;
  color: white;
  padding: 0.5rem 0.75rem;
  font-size: 0.875rem;
}

.btn-delete:hover {
  background: #ff5252;
  transform: scale(1.05);
}

.progress-section {
  background: rgba(255, 255, 255, 0.1);
  padding: 1.5rem;
  border-radius: 12px;
  backdrop-filter: blur(10px);
}

.progress-bar {
  width: 100%;
  height: 8px;
  background: rgba(255, 255, 255, 0.3);
  border-radius: 4px;
  overflow: hidden;
  margin-bottom: 0.75rem;
}

.progress-fill {
  height: 100%;
  background: white;
  border-radius: 4px;
  transition: width 0.3s ease;
}

.progress-text {
  text-align: center;
  color: white;
  margin: 0;
  font-size: 0.875rem;
  font-weight: 600;
}

/* Responsive Design */
@media (max-width: 640px) {
  .task-manager {
    padding: 1rem;
  }

  .header h1 {
    font-size: 2rem;
  }

  .stat-value {
    font-size: 1.5rem;
  }

  .input-section {
    flex-direction: column;
  }

  .btn-add {
    width: 100%;
  }
}
</style>
