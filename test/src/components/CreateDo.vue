<script setup>
import {ref} from 'vue'

const props = defineProps(["idInDoList"])

const emit = defineEmits(['addDo'])

const doText = ref("")


const addDo = () => {
    if(doText.value != ""){
      emit('addDo', props.idInDoList, doText.value)
    }
     
    doText.value = ""
  }

</script>

<template>
      <div
        class="mt-4 row d-flex justify-content-center">
    <input 
    v-model="doText"
    maxlength="35"
    type="text" style="width: 40%;" class="form-control"
    placeholder="Введите дело">
  </div>
   
  <br>

  <button @click="addDo"  type="button" style="position: relative;;left: 50%; transform: translate(-50%, 0);" class="btn btn-success mt-2  btn-lg">Отправить</button>
</template>

<style>
    .btn-lg{
        position: relative;
        width: 30%;
    }

    .form-control:focus {
        border-color: rgb(0, 128, 49);
        box-shadow: inset 0 1px 1px rgb(0, 128, 49), 0 0 8px rgb(0, 128, 49);
    }

    .form-control{
        border-color: rgb(0, 128, 49);
    }
</style>