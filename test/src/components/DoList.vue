<script setup>

const props = defineProps(["doList"])

const emit = defineEmits(["delDo"])

const delDo = (id) => {
  emit("delDo", id)
}

</script>

<template>
    <br>

    <div v-for="doItem in props.doList">
      <div class="to-do-border mt-3">
        <button @click="delDo(doItem.id)" class="del-btn btn btn-success mt-1 me-1">Удалить</button>
        <br><br>
        <span style="font-size: 20px;">{{ doItem.text }}</span>
        <br><br>
      </div>
    </div>
</template>

<style>
    .to-do-border{
    text-align: center;
    display: block;
    position: relative;
    left: 50%;
    border-radius: 10px;
    transform: translate(-50%, 0);
    width: 40%;
    border: 3px solid rgb(0, 128, 49) 
  }

  .del-btn{
    float: right;
  }
</style>