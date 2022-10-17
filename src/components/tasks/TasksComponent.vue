<template>
 
    <div :key="task.id" v-for="task in tasks">
    <TaskDetails @complete-task="$emit('complete-task',task.id)" @delete-task="$emit('delete-task',task.id)" :task="task" />

  </div>
</template>

<script>
import TaskDetails from './TaskDetails.vue';
export default {
    name: "TasksComponent",
    components: { TaskDetails },
    props:{
      tasks:Array,
    }
}
</script>

<style>

</style>