<template>
  <v-app>

    <v-card>
      <v-app-bar absolute app class="warning">
        <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>
        <v-toolbar-title>Vuetify  </v-toolbar-title>
        <v-spacer></v-spacer>
        <v-btn small class="success ma-2">Ingreso</v-btn>
        <v-btn  small class="error " >Salir</v-btn>        
      </v-app-bar>
  
      <v-navigation-drawer app v-model="drawer" temporary dark>
        <v-layout mt-4 column align-center>
          <v-flex>
            <v-avatar>
              <img src="https://randomuser.me/api/portraits/men/81.jpg" alt="">
            </v-avatar>
          </v-flex>
          <v-flex>
            <p class="white--text mt-3 headline">Nombre Prueba</p>
          </v-flex>
        </v-layout>
        <v-row>
          <v-col class="ma-5">
            <v-btn color="success " :to="{name: 'Home'}"  block>Home</v-btn>
            <v-btn color="success mt-2" :to="{name: 'Tareas'}" block>Lista de tareas</v-btn>
          </v-col>
        </v-row>
      </v-navigation-drawer>
    </v-card>

    <v-main>
      <router-view/>  
    </v-main>

  </v-app>

</template>

<script>

export default {
  name: 'App',
  data: () => ({
    drawer: true
  }),
};
</script>
