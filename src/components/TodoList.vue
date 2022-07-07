<template>
<ul class="task-list" v-if="tasks.length">
  <li class="task" v-for="(task, index) in tasks" :key="task">
    <p>#{{index + 1}}</p>
    <p>{{task.text}}</p>
    <button class="delete-button" @click="$emit('deleteTask', task)" />
  </li>
</ul>
<p class="message" v-else>Задач пока нет, добавьте новую</p>
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

<style lang="css">
.task-list {
  list-style: none;
  padding: 0 20px;
}

.task {
  text-align: left;
  margin: 10px 0;
  display: flex;
}

.task p:first-child {
  margin-right: 20px;
}

.message {
  text-align: center;
  margin: 10px 0;
}

.task button {
  margin: auto;
  margin-right: 0;
}

.delete-button {
  position: relative;
  top: -1px;
  width: 1.5rem;
  height: 1.5rem;
  opacity: 0.5;
  transition: opacity ease 0.5s;
  background-color: inherit;
  border: none;
  outline: none;
  cursor: pointer;
}

.delete-button:hover {
  opacity: 1;
}

.delete-button::before,
.delete-button::after {
  content: '';
  position: absolute;
  left: -2px;
  display: block;
  width: 1.5rem;
  height: 3px;
  background: red;
}

.delete-button::before {
  transform: rotate(45deg);
}

.delete-button::after {
  transform: rotate(-45deg);
}

.delete-button::focus::before,
.delete-button::focus::after {

  background: rgb(0, 0, 90);
}

@media (max-width: 450px),
(max-width: 750px) and (max-height: 750px) {
  .task-list {
    padding: 40px 20px;
  }
}
</style>
