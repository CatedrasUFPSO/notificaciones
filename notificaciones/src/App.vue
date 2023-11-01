<script setup>
import { ref } from 'vue'

let notifications = ref(100)

function addValue() {
  notifications.value++
  console.log(notifications)
}

function minusValue() {
  if (notifications.value >= 1) {
    notifications.value--
  }
}

addValue()
</script>

<template>
  <div class="wrapper">
    <div class="profile">
      <div class="notification" v-show="notifications > 0">{{ notifications }}</div>
    </div>
    <div class="button-wrapper">
      <div class="button" @click="minusValue">-</div>
      <div class="button" @click="addValue">+</div>
    </div>
    <div v-if="notifications == 0">Buuu! nadie te escribe 🤣</div>
    <div v-else>Revisa tu inbox 😊</div>
  </div>
</template>

<style scoped>
.wrapper {
  background-color: #348888;
  width: 60%;
  border-radius: 8px;
  margin: 0 auto;
  padding-top: 32px;
  overflow: hidden;
}

.profile {
  background-color: purple;
  width: 120px;
  height: 120px;
  border-radius: 100%;
  margin: 0 auto;
  position: relative;
  background-image: url('https://media.licdn.com/dms/image/C4E03AQFNPQN4lAxjtw/profile-displayphoto-shrink_800_800/0/1626457592707?e=2147483647&v=beta&t=ujLEatxPeialHJWdf11PlJCLrmDnV_zspLc1KP1Z3M0');
  background-size: cover;
}

.notification {
  position: absolute;
  padding: 2px;
  background-color: #f24405;
  min-width: 18px;
  height: 18px;
  border-radius: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  color: white;
  top: 0;
  right: 0;
}

.button-wrapper {
  margin-top: 12px;
  text-align: center;
  padding-bottom: 16px;
}

.button {
  background-color: #fa7f08;
  border-radius: 4px;
  padding: 2px 0;
  font-weight: bold;
  color: white;
  width: 40px;
  cursor: pointer;
  display: inline-block;
}

.button:first-child {
  margin-right: 8px;
}

.button:last-child {
  margin-left: 8px;
}
</style>
