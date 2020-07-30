<template>     
  <div clas="todo-list">
    <TodoItem 
      v-for="todo in todos"
      :key="todo._id"
      :title="todo.title"
      :description="todo.desription"
    />

  </div>
</template>

<script>
import TodoItem from '@/components/TodoItem'

export default {
  name: 'App',
  props: {
    todos: {
      required: true,
      type: Array
    }
  },
  components: {
    TodoItem
  },
} 
</script>
 
<style scoped>
  .todo-list {
    flex: 1;
  }
</style>
