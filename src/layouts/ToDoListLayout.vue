<template>
    <div>
      <h1>To Do List xixixi</h1>
      <q-layout>
        <FormInput @addTask="addTask" />
        <ul>
          <li v-for="(todo, index) in todos" :key="index">
            <input type="checkbox" v-model="todo.completed" />
            <span :class="{ completed: todo.completed }">{{ todo.text }}</span>
            <button @click="removeTask(index)">Delete</button>
          </li>
        </ul>
      </q-layout>
    </div>
  </template>
  
  <script lang="ts">
  import { defineComponent, ref } from 'vue';
  import FormInput from 'src/components/FormInput.vue';
  
  export default defineComponent({
    name: 'ToDoListLayout',
    components: {
      FormInput
    },
    setup() {
      const todos = ref<{ text: string, completed: boolean }[]>([]);
        
      const addTask = (task: string) => {
        todos.value.push({ text: task, completed: false });
        console.log('the list:', todos.value)
      };
  
      const removeTask = (index: number) => {
        todos.value.splice(index, 1);
      };

      return {
        todos,
        addTask,
        removeTask
      };
    }
  });
  </script>
  
  <style>
    .completed {
      text-decoration: line-through;
    }

    #main-section{
      display: flex;
      justify-content: center;
      padding:  10px 10px 10px 10px;
    }
  </style>
  