<template>
  <button :style="{background:color}" class="btn">{{title}}</button>
</template>

<script>
export default {
    name: 'ButtonComponent',
props:{
    title:String,
    color:String
}
}
</script>

<style>

</style>