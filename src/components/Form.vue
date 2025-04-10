<script setup>
 const props = defineProps(['cadastraTarefa', 'tarefaTemp', 'trocarFiltro', 'editaTarefaTemp'])
</script>

<template>
 <form @submit.prevent="props.cadastraTarefa">
  <div class="row">
   <div class="col">
    <input :value="props.tarefaTemp" @change="props.editaTarefaTemp" required type="text"
     class="form-control" placeholder="Enter your task here">
   </div>
   <div class="col-md-1">
    <button type="submit" class="btn btn-primary">
     To add
    </button>
   </div>
   <div class="col-md-2">
    <select @change="props.trocarFiltro" class="form-control">
     <option value="todas">
      All
     </option>
     <option value="pendentes">
      Pending
     </option>
     <option value="finalizadas">
      Completed
     </option>
    </select>
   </div>
  </div>
 </form>
</template>