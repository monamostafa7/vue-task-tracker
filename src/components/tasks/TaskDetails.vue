<template>
  <div @dblclick="$emit('complete-task',id)" :class="[task.completed?'reminder':'','task']">
    <div class="taskContent">
    <h3>{{task.name}}</h3>
    <p>{{task.decs}}</p>
    </div>
    <i @click="onDelete(task.id)" class="fa-solid fa-xmark"></i>
  </div>
</template>

<script>
export default {
 name:'TaskDetails',
 props:{
    task:Object,
 },
 methods:{
    onDelete(id){
        this.$emit('delete-task',id)
    }
}
}
</script>

<style>
.task{
 background:#eee;
 padding:1%;
margin-bottom: 1%;
display: flex;
/* flex-wrap: wrap; */
justify-content:space-between; 
}
h3{
    padding:0;
    margin:0
}
i{
    align-self:center;
    color:red
}
.taskContent{
    width:80%
}
p{
    font-size:12px
}
.reminder{
    border-left: 3px solid green ;
}
</style>