<template>
  <div>
    <v-list-item
    :class="{'green lighten-4':tarefa.concluido}"
    @click="$store.dispatch('concluirTarefa', tarefa)"
    >
      <template v-slot:default="{}">
        <v-list-item-action>
          <v-checkbox :input-value="tarefa.concluido"></v-checkbox>
        </v-list-item-action>

        <v-list-item-content>
          <v-list-item-title
          :class="{'text-decoration-line-through' :tarefa.concluido}"
          class="font-weight-medium"
          >{{tarefa.titulo}}</v-list-item-title>
        </v-list-item-content>

        <v-list-item-action>
          <!--<v-btn 
          icon
          @click.stop="funcRemoveTarefa(tarefa.id)"
          >
            <v-icon color="grey darken-1">mdi-dots-vertical</v-icon>
          </v-btn>-->
          <TarefaMenu :tarefa="tarefa"/>
        </v-list-item-action>
      </template>
    </v-list-item> 
    <v-divider></v-divider>
  </div>
  
</template>

<script>
import TarefaMenu from './TarefaMenu.vue'

export default {
  components:{ TarefaMenu },
  props: ['tarefa'],
  methods:{
    funcRemoveTarefa(id){
      this.$store.commit('removeTarefa', id)

    }
  }

}
</script>

<style>

</style>