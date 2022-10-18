<template>
  <div class="d-flex">
    <form @submit.prevent="onSubmit">
  <div class="mb-3">
    <label for="taskname" class="form-label">name</label>
    <input type="text" v-model="name" class="form-control" id="taskname" aria-describedby="emailHelp">
  </div>
  <div class="mb-3">
    <label for="descrption" class="form-label">descrption</label>
    <input type="text"  v-model="descrption" class="form-control" id="descrption">
  
    
  </div>
  <button type="submit" class="btn btn-primary">Submit</button>
</form>
  </div>
</template>

<script>
export default {
  name:'CreateTask',
  props:{
    numberoftasks:String
  },
  data(){
    return {
      name: '',
      descrption:'',
      completed:false,
      
    }
  },
  methods:{
    onSubmit(){
    if(!this.name){
      alert('Please add a task')
      return
    }
    const newTask={
      id:this.numberoftasks+1,
      name:this.name,
      decs:this.descrption,
      completed:this.completed
    }
    console.log(newTask)
    this.$emit('add-task',newTask)
    this.name=''
    this.descrption=''
    },
   
     
  }
}
</script>

<style>

</style>