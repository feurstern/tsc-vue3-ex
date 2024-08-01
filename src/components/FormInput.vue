<template>
    <div>
      <label for="act" id="name">Input your To Do List:</label>
      <input v-model="newTask" type="text" id="act" @keyup.enter="submitTask" />
      <button @click="submitTask">Submit</button>
    </div>
  </template>
  
  <script lang="ts">
  import { defineComponent, ref } from 'vue';
  import Swal from 'sweetalert2';

  export default defineComponent({
    name: 'FormInput',
    emits: ['addTask'],
    setup(props, { emit }) {

      const newTask = ref('');
  
      const submitTask = () => {
        if (newTask.value.trim() !== '') {
            console.log('new task', newTask.value);
          emit('addTask', newTask.value);
          newTask.value = '';
          Swal.fire({
             text:'The data has been submit successfully',
             icon:'success',
             title:'Success'
          }) 
          
        }
        else{
            Swal.fire({
                text : 'The data should not be empty!',
                icon : 'error',
                title : 'Error'
            })
        }
      };
  
      return {
        newTask,
        submitTask
      };
    }
  });
  </script>
  