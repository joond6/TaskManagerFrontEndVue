<template>
  <div :class="['task-item', getStatusColorClass()]">
    <strong>{{ task.title }}</strong>
    <p>Description: {{ task.description }}</p>
    <p>Creator: {{ task.creator }}</p>
    <p>Created on: {{ formatDate(task.createdOn) }}</p>
    <p>Priority: {{ task.priority }}</p>
    <p>Status: {{ task.status }}</p>
  </div>
</template>

<script>
export default {
  props: {
    task: Object,
  },
  methods: {
    formatDate(dateString) {
      const options = { year: 'numeric', month: 'long', day: 'numeric' };
      return new Date(dateString).toLocaleDateString(undefined, options);
    },
    getStatusColorClass() {
      return {
        'completed-status': this.task.status === 'completed',
        'in-progress-status': this.task.status === 'in_progress',
        'pending-status': this.task.status === 'pending',
        'not-started-status': this.task.status === 'not_started',
        
        
      }},
  },
};
</script>

<style scoped>
.task-item {
  padding: 10px;
  border-radius: 5%;
  animation: mymove 3s infinite;
  box-shadow: 10px 20px 30px grey;
}
@keyframes mymove {
  50% {box-shadow: 10px 20px 30px lightseagreen;}
}
.completed-status {
  background-color: #dff0d8; 

}


.in-progress-status {
  background-color: #fcf8e3; 
}
.pending-status{
  background-color: #007bff;
}
.not-started-status{
  background-color: #6c757d;
}

/* Add more styles as needed */
</style>
