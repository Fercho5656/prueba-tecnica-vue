<template>
  <v-app>
    <v-main>
      <v-container>
        <v-row>
          <v-col cols="4">
            <contact-list/>
          </v-col>
          <v-col>
            <chat-window/>
          </v-col>
        </v-row>
      </v-container>
    </v-main>
  </v-app>
</template>

<script setup>
import ContactList from './components/ContactList.vue'
import ChatWindow from './components/ChatWindow.vue'
</script>

<style scoped>
</style>
