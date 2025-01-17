<script setup>
  import {ref} from 'vue'
  import CreateDo from './components/CreateDo.vue';
  import DoList from './components/DoList.vue';

  const doList = ref([])

  const addtoDoList = (index, text) => {
    doList.value.push({
        id: index,
        text: text
    })
  }

  const delInDoList = (id) => {
    console.log(id)
    doList.value.splice(id, 1)
    doList.value.forEach((obj) => {
        if(obj.id >= id){
          obj.id--;
        }
    })
  }

  

</script>

<template>

  <CreateDo :id-in-do-list="doList.length" @add-do="addtoDoList"/>

  <DoList :do-list="doList", @del-do="delInDoList"/>
  

</template>

<style scoped>

</style>
