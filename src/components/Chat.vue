<template>
  <chat-list-container>
    <div class="wrapper">
      <div class="icon">
        <v-icon :icon="props.icon" color="white"></v-icon>
      </div>
      <div class="">
        <p class="name">{{ props.name }}</p>
        <p class="last-message">{{ props.lastMessage }}</p>
      </div>
      <div class="">
        <p>{{ lastMessageDateComp }}</p>
      </div>
    </div>
  </chat-list-container>
</template>

<script setup>
import ChatListContainer from './ChatListContainer.vue';
import { computed } from 'vue';

const props = defineProps({
  icon: String,
  name: String,
  lastMessage: String,
  lastMessageDate: Date
})

const lastMessageDateComp = computed(() => {
  const month = ['Jan',
    'Feb',
    'March',
    'April',
    'May',
    'Jun',
    'Jul',
    'Aug',
    'Sep',
    'Oct',
    'Nov',
    'Dec'][props.lastMessageDate.getMonth()]
  return `${month} ${props.lastMessageDate.getUTCDate()}`
})
</script>

<style scoped>
.wrapper {
  display: flex;
  align-items: center;
  gap: 8px;
}

.icon {
  background-color: #333;
  border-radius: 50%;
  padding: 0.5rem;
}

.name {
  font-size: 1rem;
  font-weight: 500;
}

.last-message {
  font-weight: 400;
}
</style>