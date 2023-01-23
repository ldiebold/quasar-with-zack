<script setup>
import { ref } from 'vue'

const todo = ref('')

const todos = ref([])
</script>

<template>
  <q-page class="flex flex-center">
    <q-input
      v-model="todo"
      label="My Input"
      outlined
      color="blue-9"
    />

    <q-btn
      label="submit"
      color="green"
      unelevated
      :loading="loading"
      @click="() => {
        todos.push({
          done: false,
          title: todo
        })
        todo = ''
      }"
    />

    <pre>{{ todos }}</pre>
  </q-page>
</template>
