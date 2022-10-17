<template>
  <header><h1>Task Tracker</h1>
  <ButtonComponent title="Add Task" color='#000'/>
  </header>
</template>

<script>
import ButtonComponent from './ButtonComponent.vue';
export default {
    name: "HeaderComponent",
    components: { ButtonComponent }
}
</script>

<style scoped >
header{
display:flex;
justify-content:space-between;
align-items:center;
margin-bottom: 20px;

}
</style>