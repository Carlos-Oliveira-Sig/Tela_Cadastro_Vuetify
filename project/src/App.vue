<template>
  <v-app>
      <v-app-bar app flat class="white">
        <v-text-field class="pa-5"
            hide-details
            prepend-icon="mdi-magnify"
            solo
            flat
            label="Pesquise por nome ou Skills"
            clearable
        >
        </v-text-field>
      </v-app-bar>
      
      <v-main class="grey lighten-3">
        <v-card class="transparent" flat>
          <router-view/>
        </v-card>      
      </v-main>
  </v-app>
</template>

<script>

export default {
  name: 'App',

  data: () => ({
    //
  }),
};
</script>
