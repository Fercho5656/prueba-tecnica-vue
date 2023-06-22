<template>
  <v-container class="container">
    <slot />
  </v-container>
</template>

<script setup>
</script>

<style scoped>
.container {
  display: flex;
  align-items: center;
  gap: 8px;
  cursor: pointer;
  transition: 0.15s;
  border-radius: 5px;
  color: #999;
}

.container:hover {
  color: #fff;
  background-color: #aa7dfd;
}

.container.active {
  color: #fff;
  background-color: #aa7dfd;
  box-shadow: rgba(0, 0, 0, 0.16) 0px 1px 4px;
}

</style>