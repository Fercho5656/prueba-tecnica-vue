<template>
  <v-conteiner>
    <header>
      <div class="user-chat">
        <div class="icon">
          <v-icon icon="mdi-account" color="white"></v-icon>
        </div>
        <div class="user-chat-info">
          <p class="user-name">Gavin Griffith</p>
          <p>Frontend Developer</p>
        </div>
      </div>
      <div class="actions">
        <v-btn variant="plain" icon="mdi-phone"></v-btn>
        <v-btn variant="plain" icon="mdi-video"></v-btn>
        <v-btn variant="plain" icon="mdi-magnify"></v-btn>
        <v-btn variant="plain" icon="mdi-dots-vertical"></v-btn>
      </div>
    </header>
    <div class="chat-content">
      <div v-for="message in messages" :class="`${message.isMine ? 'message mine' : 'message not-mine'}`">
        <div class="message-container">
          <div class="icon">
            <v-icon icon="mdi-account" color="white"></v-icon>
          </div>
          <div class="">
            <p class="message-content">{{ message.message }}</p>
          </div>
        </div>
        <p class="date">{{ message.date }}</p>
      </div>
    </div>
    <form class="input">
      <v-text-field label="Type your message..." :rules="messageRules">
      </v-text-field>
      <v-btn variant="plain" icon="mdi-microphone-outline"></v-btn>
      <v-btn variant="plain" icon="mdi-attachment"></v-btn>
      <v-btn color="#aa7dfd">Send</v-btn>
    </form>
  </v-conteiner>
</template>

<script setup>
const messages = [
  {
    isMine: true,
    message: 'How can we help?',
    date: '1:45 AM'
  },
  {
    isMine: false,
    message: 'Hey John! I am looking for the best admin template',
    date: '1:45 AM'
  },
  {
    isMine: true,
    message: 'Absolutely! Our admin is the responsive admin template',
    date: '1:46 AM'
  },
  {
    isMine: false,
    message: 'Looks clean and fresh UI. 😍',
    date: '1:46 AM'
  },
]

const messageRules = [
  value => {
    if (value !== ' ') return true
    return ''
  }
]
</script>

<style scoped>
header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  background-color: #f7f7f8;
  padding: 1rem;
  padding-bottom: 3rem;
  border-bottom: solid 2px #eee;
}

.user-chat {
  display: flex;
  align-items: center;
  gap: 8px;
}

.user-chat-info {
  color: #aaa;
}

.user-name {
  font-weight: 500;
}

.icon {
  padding: 0.5rem;
  background-color: #333;
  border-radius: 50%;
}

.chat-content {
  display: flex;
  flex-flow: column nowrap;
  gap: 1rem;
  background-color: #f7f7f8;
  padding: 1rem;
}

.message {
  display: flex;
  align-items: center;
  flex-flow: column nowrap;
  padding: 0.5rem;
  gap: 8px;
}

.message-container {
  display: flex;
  align-items: center;
  gap: 8px;
}

.mine {
  margin-left: auto;
  flex-flow: column;
}

.mine .message-container {
  flex-flow: row-reverse;
}

.not-mine {
  margin-right: auto;
}

.mine .message-content {
  color: #fff;
  background-color: #aa7dfd;
  border-top-right-radius: 0;
}

.not-mine .message-content {
  background-color: #fff;
  border-top-left-radius: 0;
}

.message-content {
  padding: 1rem;
  border-radius: 5px;
  box-shadow: rgba(0, 0, 0, 0.16) 0px 1px 4px;
}

.date {
  margin: inherit;
}

.input {
  display: flex;
  align-items: flex-start;
  padding: 0 2rem;
  background-color: #f7f7f8;
}
</style>