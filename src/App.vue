<template>
  <div class="container">
    <todo-form
      @addTask="addTask"
    />
    <todo-list
      :tasks="tasks"
    />
  </div>
</template>

<script>
import TodoForm from '@/components/TodoForm'
import TodoList from '@/components/TodoList'

export default {
  components: {
    TodoForm,
    TodoList,
  },
  data() {
    return {
      tasks: [
        { text: 'Помыть посуду' },
        { text: 'Убрать в комнате' },
      ],
    }
  },
  methods: {
    addTask(task) {
      this.tasks.push(task)
    },
  },
}
</script>

<style lang="css">
* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
  font-family: Arial, Helvetica, sans-serif;
}

.container {
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>
