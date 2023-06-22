<template>
  <chat-list-container>
    <div class="icon-wrapper">
      <v-icon :icon="props.icon" color="white"></v-icon>
    </div>
    <div class="">
      <p class="name">{{ props.name }}</p>
      <p class="status">{{ props.status }}</p>
    </div>
  </chat-list-container>
</template>

<script setup>
import ChatListContainer from './ChatListContainer.vue';
const props = defineProps({
  icon: String,
  name: String,
  status: String
})
</script>

<style scoped>
.icon-wrapper {
  background-color: #333;
  border-radius: 50%;
  padding: 0.5rem;
}

.name {
  font-weight: 500;
}

.status {
  font-weight: 300;
}
</style>