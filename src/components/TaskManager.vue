<template>
    <div class="taskmanagerclass">
      <p>
      Welcome to Task Manager Application</p>
      <task-list :tasks="tasks" />
    </div>
  </template>
  
  <script>
  import TaskList from './TaskList.vue';
  
  export default {
    components: {
      TaskList,
    },
    data() {
      return {
        tasks: [],
      };
    },
    mounted() {
      this.fetchTasks();
    },
    methods: {
      async fetchTasks() {
        try {
          const response = await fetch('https://taskapp-g1gd.onrender.com/api');
          const data = await response.json();
          this.tasks = data;
        } catch (error) {
          console.error('Error fetching tasks:', error);
        }
      },
    },
  };
  </script>
  
  <style scoped>
  p {
    color: #333;
    text-align: center;
    font-size:40px ;
  }
  .taskmanagerclass{
    margin:5%;
    height:90px;
    background-color: lightcyan;
    border-radius:5%;
    box-shadow: 10px 20px 30px grey;
  }
  
  /* Add more styles as needed */
  </style>
  