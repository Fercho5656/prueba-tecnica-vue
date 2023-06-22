<template>
  <header>
    <v-icon icon="mdi-account" size="32"></v-icon>
    <v-text-field prepend-icon="mdi-magnify" label="Search...">
    </v-text-field>
  </header>
  <v-container class="chat-list-container">
    <v-row>
      <p class="title">Chats</p>
      <chat v-for="(chat, idx) in chats" @click="activeChat = idx" :class="`${idx === activeChat ? 'active' : ''}`"
        :icon="chat.icon" :name="chat.name" :last-message="chat.lastMessage" :last-message-date="chat.lastMessageDate" />
    </v-row>
    <v-row>
      <p class="title">Contacts</p>
      <contact v-for="contact in contacts" :icon="contact.icon" :name="contact.name" :status="contact.status" />
    </v-row>
  </v-container>
</template>

<script setup>
import Chat from './Chat.vue'
import Contact from './Contact.vue'
import { ref } from 'vue';

const chats = [
  {
    icon: 'mdi-account',
    name: "Givin Griffith",
    lastMessage: "I will purchase it for sure. 👍",
    lastMessageDate: new Date()
  },
  {
    icon: 'mdi-account',
    name: "Givin Griffith",
    lastMessage: "I will purchase it for sure. 👍",
    lastMessageDate: new Date()
  },
  {
    icon: 'mdi-account',
    name: "Givin Griffith",
    lastMessage: "I will purchase it for sure. 👍",
    lastMessageDate: new Date()
  }
]
const contacts = [
  {
    icon: 'mdi-account',
    name: "Givin Griffith",
    status: 'Cake pie jelly jelly beans'
  },
  {
    icon: 'mdi-account',
    name: "Givin Griffith",
    status: 'Cake pie jelly jelly beans'
  },
  {
    icon: 'mdi-account',
    name: "Givin Griffith",
    status: 'Cake pie jelly jelly beans'
  }
]

const activeChat = ref(0);
</script>

<style scoped>
header {
  display: flex;
  align-items: center;
  border: solid 2px #eee;
  border-top-left-radius: 5px;
  border-top-right-radius: 5px;
  padding: 1rem;
}

.title {
  font-size: 1.5rem;
  color: #aa7dfd;
  font-weight: 500;
}

.chat-list-container {
  padding: 1.5rem;
  border: solid 2px #eee;
  border-top: none;
}
</style>