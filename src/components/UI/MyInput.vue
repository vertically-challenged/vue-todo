<template>
<input class="my-input" :placeholder="placeholder" :value="modelValue" @input="updateInput" />
</template>

<script>
export default {
  name: 'my-input',
  props: {
    modelValue: [String, Number],
    placeholder: String,
  },
  methods: {
    updateInput(event) {
      this.$emit('update:modelValue', event.target.value)
    },
  },
}
</script>

<style lang="css">
.my-input {
  width: 95%;
  background: inherit;
  border: none;
  border-bottom: solid 2px #fff;
  color: #fff;
  font-size: 1rem;
  padding-top: 10px;
  padding-bottom: 10px;
  outline: none;
}

.my-input::placeholder {
  color: #fff;
  opacity: .8;
}

.my-input:focus {
  border-bottom: solid 2px rgb(0, 0, 90);
}

.my-input:focus::placeholder {
  color: rgb(0, 0, 90);
  opacity: .8;
}
</style>
