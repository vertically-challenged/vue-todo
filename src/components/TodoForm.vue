<template>
  <div>
    <form @submit.prevent>
      <my-input v-model="task.text"/>
      <my-button @click="addTask">Добавить задачу</my-button>
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
    }
  },
  methods: {
    addTask() {
      this.$emit('addTask', { ...this.task })
      this.task.text = ''
    },
  },
}
</script>
