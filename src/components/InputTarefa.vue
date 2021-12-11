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
  </div>
</template>

<script>
export default {
  data() {
    return{
      campoInput: null,
    }
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

<style>

</style>