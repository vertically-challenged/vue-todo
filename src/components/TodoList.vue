<template>
  <ul>
    <li
      v-for="(task, index) in tasks"
      :key="task"
    >
      <h2>Задача № {{index + 1}}</h2>
      <p>{{task.text}}</p>
    </li>
  </ul>
</template>

<script>
export default {
  props: {
    tasks: {
      type: Array,
      required: true,
    },
  },
}
</script>
