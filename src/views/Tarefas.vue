<template>
  <div>
    <v-col
      cols="12"
    >
      <v-text-field
        v-model="campoInput"
        label="Digite uma Tarefa"
        outlined
        clearable
        @keyup.enter="funcAddTarefa"
      ></v-text-field>
    </v-col>
    
    <ListaTarefas/>
  </div>
  
</template>

<script>
  import ListaTarefas from '../components/terefas/ListaTarefas.vue'

  export default {
    name: 'Home',

    components: {
      ListaTarefas
    },
    data() {
      return{
        campoInput: null,
      }
    },
    created(){
      this.$store.commit('buscarTarefas')
    },
    methods:{
      funcAddTarefa(){
        //this.$store.commit('adicionaTarefa',this.campoInput)
        this.$store.dispatch('adicionaTarefa',this.campoInput)
        this.campoInput = null
        
      }
    }
  }
</script>
