<template>
  <main>
    <div class="details-container">
      <UserLoc v-for="(userLoc, index) in usersLoc" :key="index" :usersLoc="userLoc" :showValue="index <= currentLocIndex" :index="index" :completed="userLoc.showCompleted" />
      <UserInfo v-for="(userInfo, index) in usersInfo" :key="index" :usersInfo="userInfo" :showValue="index <= currentDeviceIndex" :index="index" :completed="userDevice.showCompleted"/>
      <UserDevice v-if="showDevice" v-for="userDevice in usersDevice" :key="userDevice.label" :usersDevice="userDevice" />
    </div>
  </main>
</template>

<script setup>
import { ref, onMounted } from 'vue'
import UserLoc from './components/initial/UserLoc.vue'
import UserInfo from './components/initial/UserInfo.vue'
import UserDevice from './components/initial/UserDevice.vue'
import "./style.css"

const usersLoc = ref([
  { label: "IP Address", value: "10.37.196.70", showCompleted: false},
  { label: "City", value: "Provo", showCompleted: false},
  { label: "Region", value: "Utah", showCompleted: false},
  { label: 'ZIP', value: '84606', showCompleted: false},
  { label: 'Country', value: 'United States', showCompleted: false},
])

const currentLocIndex = ref(-1);

const usersInfo = ref([
  { label: 'School', value: 'Brigham Young University', showCompleted: false},
  { label: 'Name', value: 'John Doe', showCompleted: false},
  { label: 'Phone Number', value: '(555) 555-5555', showCompleted: false},
  { label: 'Email', value: 'X5k6Z@example.com', showCompleted: false},
])

const usersDevice = ref([
  { label: 'Password', value: '********' },
  { label: 'Username', value: 'johndoe' },
])

const showInfo = ref(false)
const showDevice = ref(false)

onMounted(() => {
  const intervalId = setInterval (() => {
    currentLocIndex.value += 1;
    if (currentLocIndex.value > usersLoc.value.length - 1) {
      clearInterval(intervalId);
    } else {
      usersLoc.value[currentLocIndex.value].showCompleted = true;
    }
  }, 300)
  setTimeout(() => {
    showInfo.value = true;
  }, 3000)
  setTimeout(() => {
    showDevice.value = true
  }, 3000)
});
</script>