<template>
<div class="container">
  <todo-form @addTask="addTask" />
  <todo-list :tasks="tasks" @deleteTask="deleteTask" />
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
      tasks: [],
    }
  },
  methods: {
    addTask(task) {
      this.tasks.push(task)
    },
    deleteTask(task) {
      console.log(task)
      this.tasks = this.tasks.filter((item) => (item.id !== task.id))
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

body {
  background: rgb(58, 58, 58);
}

.container {
  margin: auto;
  margin-top: 20px;
  padding: 10px;
  font-size: 16px;
  background-color: rgb(85, 85, 85);
  color: #fff;
}

@media (max-width: 450px),
(max-width: 750px) and (max-height: 750px) {
  body {
    background-color: rgb(85, 85, 85);
  }

  .container {
    margin-top: 0;
  }
}

@media (min-width: 660px) {
  .container {
    max-width: 800px;
    padding:  10px 0;
  }
}
</style>
