<script setup>
const props = defineProps(['tarefas'])
</script>

<template>
 <ul class="list-group mt-4">
  <li class="list-group-item" v-if="props.tarefas.length > 0" v-for="tarefa in props.tarefas" :key="tarefa.titulo">
   <input @change="evento => tarefa.finalizada = evento.target.checked" :checked="tarefa.finalizada" :id="tarefa.titulo"
    type="checkbox">
   <label :for="tarefa.titulo" :class="{ done: tarefa.finalizada }" class="ms-3">
    {{ tarefa.titulo }}
   </label>
  </li>
  <li v-else>
   <h3>
    There are no tasks here.
   </h3>
  </li>
 </ul>
</template>

<style scoped>
.done {
 text-decoration: line-through;
}

ul {
 list-style-type: none;
}
</style>