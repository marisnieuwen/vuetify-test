<template>
  <v-app :theme="theme">
    <v-container >
    <v-app-bar title="Test">
      <v-btn stacked>
          <v-icon icon="mdi-speedometer"></v-icon>

        Monitor
      </v-btn>

      <v-btn stacked>
        <v-badge color="error" content="5" >
          <v-icon icon="mdi-server"></v-icon>
        </v-badge>

        Servers
      </v-btn>

      <v-btn stacked>
        <v-badge color="error" content="2">
          <v-icon icon="mdi-web"></v-icon>
        </v-badge>

        Websites
      </v-btn>

      <v-btn stacked>
        <v-icon icon="mdi-folder-outline"></v-icon>

        Projects
      </v-btn>
      <v-spacer></v-spacer>

      <v-btn :prepend-icon="theme === 'light' ? 'mdi-weather-sunny' : 'mdi-weather-night'" @click="onClick"></v-btn>
    </v-app-bar>

    <v-main>
      
    <DataTable />
    </v-main>
  </v-container>
  </v-app>

</template>


<script setup>
import DataTable from '@/components/DataTable.vue'
import { ref } from 'vue'

const theme = ref('dark')

function onClick () {
  theme.value = theme.value === 'light' ? 'dark' : 'light'
}
</script>
