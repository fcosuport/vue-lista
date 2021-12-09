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
    <v-list
      flat
      subheader
    >
      <v-list-item-group
        multiple
        active-class=""
      >
      <div
      v-for="tarefa, index in $store.state.tarefas" :key="index"
      >
        <Tarefa :tarefa="tarefa"/>
      </div>
      </v-list-item-group>
    </v-list>
  </div>
  
</template>

<script>
  import Tarefa from '../components/terefas/Tarefa.vue'

  export default {
    name: 'Home',

    components: {
      Tarefa
    },
    data() {
      return{
        campoInput: null,
      }
    },
    methods:{
      funcAddTarefa(){
        this.$store.commit('adicionaTarefa',this.campoInput)
        this.campoInput = null
        
      }
    }
  }
</script>
