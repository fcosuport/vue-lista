<template>
  <v-app id="inspire">
    <!--<v-navigation-drawer
      v-model="drawer"
      app
    >
        
    </v-navigation-drawer>-->
    <v-navigation-drawer
      v-model="drawer"
      app
    >
    <v-img
    src="./assets/logopratico.jpg"
    gradient="to top right, rgba(19,84,122,.5), rgba(128,208,199,.8)"
    dark
    class="pt-5 text-center"
    >
      <v-list-item>
        <v-list-item-content>
          <v-list-item-title class="text-h6">
            Lista de Tarefas
          </v-list-item-title>
          <!--<v-list-item-subtitle>
            Lista de Tarefas
          </v-list-item-subtitle>-->
        </v-list-item-content>
      </v-list-item>
    </v-img>

      <v-divider></v-divider>

      <v-list
        dense
        nav
      >
        <v-list-item
          v-for="item in items"
          :key="item.title"
          :to="item.to"
          link
        >
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <!--<v-app-bar app>
      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>

      <v-toolbar-title>Lista de Tarefas</v-toolbar-title>
    </v-app-bar> -->
    <v-app-bar
      app
      prominent
      color="#fcb69f"
      dark
      src="./assets/bg.jpg"
    >
      <template v-slot:img="{ props }">
        <v-img
          v-bind="props"
          gradient="to top right, rgba(19,84,122,.5), rgba(128,208,199,.8)"
        ></v-img>
      </template>

      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>

      <center>
        <v-app-bar-title
        >
          Lista de Tarefas
          <InputTarefa/>
        </v-app-bar-title>
      </center>

      <!--<v-spacer></v-spacer>

      <v-btn icon>
        <v-icon>mdi-magnify</v-icon>
      </v-btn>

      <v-btn icon>
        <v-icon>mdi-heart</v-icon>
      </v-btn>

      <v-btn icon>
        <v-icon>mdi-dots-vertical</v-icon>
      </v-btn>-->
    </v-app-bar>

    <v-main>
      <router-view/>
    </v-main>
  </v-app>
</template>

<script>
import InputTarefa from './components/InputTarefa.vue'
  export default {
  components: { InputTarefa },
    data: () => ({
      drawer: null,
      items: [
        { title: 'Tarefas', icon: 'mdi-view-dashboard', to:'/' },
        { title: 'Sobre', icon: 'mdi-help-box', to:'/sobre' },
      ]
    }),
  }
</script>