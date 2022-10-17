<template>
  <div class="container">
    <HeaderComponent/>
<TasksComponent @complete-task="completeTask" @delete-task="deleteTask" :tasks=tasks />
<CreateTask/>
  </div>
</template>

<script>
import HeaderComponent from './components/HeaderComponent.vue'
import TasksComponent from './components/tasks/TasksComponent.vue'
import CreateTask from './components/tasks/CreateTask.vue'

export default {
  name: 'App',
  components: {
    HeaderComponent,
    TasksComponent,
    CreateTask
},
data () {
  return{
  tasks:[]
}
},
methods:{
  deleteTask(id){
    this.tasks=this.tasks.filter((task)=>task.id!==id)
  },
  completeTask(id){
    this.tasks=this.tasks.map((task)=>task.id==id?{...task,completed:!task.completed}:task)
  }
 
},
created(){
 this.tasks=[
 {id:1,name:"task 1", completed:false, decs:"  dummy text dummy text dummy text   dummy text dummy text dummy text   dummy text dummy text dummy text  " },
  {id:2,name:"task 2", completed:true, decs:"  dummy text dummy text dummy text dummy text dummy text dummy dummy text dummy text dummy text  " },
 {id:3,name:"task 3", completed:true, decs:"  dummy text dummy text dummy text  dummy text dummy text " },
 {id:4,name:"task 4", completed:false, decs:"  dummy text dummy text dummy text   dummy text dummy text dummy text   dummy text dummy text dummy text  " }]
},

emits:['delete-task','complete-task']
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}
.container{
  border: 1px solid #eee;
  padding:2%;
  width: 50%;
 border-radius:10px;
  margin:auto;
}
.btn{
 padding:15px 20px;
 color:#FFF;
 border:none;
 border-radius:3px;

}
</style>
