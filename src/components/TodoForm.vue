<template>
<div>
  <form class="todo-form" @submit.prevent="addTask">
    <my-input v-model="task.text" :placeholder="placeholder"/>
  </form>
</div>
</template>

<script>
export default {
  data() {
    return {
      task: {
        text: '',
      },
      placeholder: 'Введите название задачи',
    }
  },
  methods: {
    addTask() {
      this.$emit('addTask', {
        id: Date.now(),
        ...this.task,
      })
      this.task.text = ''
    },
  },
}
</script>

<style lang="css">
.todo-form {
  display: flex;
  justify-content: center;
  padding-top: 20px;
  padding-bottom: 20px;
}

@media (max-width: 450px),
(max-width: 750px) and (max-height: 750px) {
  .todo-form {
    position: fixed;
    bottom: 0;
    left: 0;
    right: 0;
    background-color: rgb(85, 85, 85);
    z-index: 2;
  }
}
</style>
