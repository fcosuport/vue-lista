<template>
  <div>    
    <ListaTarefas/>
    <div
    v-if="!$store.state.tarefas.length"
    class="mt-16 animate__animated animate__bounceInUp"
    >
      <center>
        <v-icon
        size="100"
        color="primary"
        >
        mdi-check
        </v-icon>
        <div class="text-h5 primary--text">Nenhuma Tarefa</div>
      </center>
    </div>
  </div>
  
</template>

<script>
  import ListaTarefas from '../components/terefas/ListaTarefas.vue'

  export default {
    name: 'Home',

    components: {
      ListaTarefas
    },
    created(){
      this.$store.commit('buscarTarefas')
    }
  }
</script>
