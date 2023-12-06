
<template>
  <div class="tasklisth2">
  <p>Task List</p>
  </div>
    <div class="task-list">
      
        <task-item v-for="task in tasks" :key="task.id" :task="task" />
    </div>
  </template>
  
  <script>
  import TaskItem from './TaskItem.vue';
  
  export default {
    components: {
      TaskItem,
    },
    props: {
      tasks: Array,
    },
  };
  </script>
  
  <style scoped>
  /* Add your styles here */
  .task-list {
  
  display: grid;
   grid-template-columns: repeat(3, 1fr);
   gap:1%;
}
p{
  height:50px;
  text-align: center;
  font-size: 40px;
  background-color: aqua;
  margin-left:10%;
  margin-right:10%;
  border-radius:5%;
}
.tasklisth2{
  margin:2%;
  height:50px;
  background-color: lightblue;
  border-radius:5%;
  box-shadow: 10px 20px 30px grey;
}

  </style>

  