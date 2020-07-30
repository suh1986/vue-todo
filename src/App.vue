<template>
  <div id="app">
    <div class="todo-wrapper">
      <div class="todo-container">
        <TodoList :todos = "todos"/>
        <Modal
          v-on:modalClose="closeModal"
          :isOpen="isModalOpen" />
      </div>
    </div>
  </div>
</template>

<script>
import playground from './playground.js'
import TodoList from '@/components/TodoList'
import Modal from '@/components/Modal'


export default {
  name: 'App',
  components: {
    TodoList,
    Modal
  },
  data() {
    return {
      isModalOpen: false,
      todos : [
        {
          _id: '1',
          title: 'Walk the dog',
          description: 'Go to forrest near the Zoo'
        },
        {
          _id: '2',
          title: 'Buy a bread',
          description: 'Whole grain bread would be good'
        },
        {
          _id: '3',
          title: 'Learn Programming',
          description: 'Preferable Tomorrow!'
        }
      ]
    }
  },
  //this function call automatically by vue
  created() {
    playground()
  },
  methods: {
    openModal() {
      this.isModalOpen = true
    },
    closeModal() {
      this.isModalOpen = false
    }

  }
}
</script>

<style lang='scss' scoped>
  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }
  .is-primary {
    background-color: #47ca47 !important;
  }
  
  .todo {
    &-wrapper {
      /* flexible styling */
      display: flex;
      justify-content: center;
      width: 100%;
    }
    &-container {
      display: flex;
      flex-direction: column;
      width: 400px;
      min-height: 400px;
      background-color: #ededed;
      border-radius: 5px;
    }
  }
</style>
