<template>
  <main>
    <div class="details-container">
      <UserLoc v-for="userLoc in usersLoc" :key="userLoc.label" :usersLoc="userLoc" />
      <UserInfo v-for="userInfo in usersInfo" :key="userInfo.label" :usersInfo="userInfo" />
      <UserDevice v-for="userDevice in usersDevice" :key="userDevice.label" :usersDevice="userDevice" />
    </div>
  </main>
</template>

<script setup>
import { ref } from 'vue'
import UserLoc from './components/initial/UserLoc.vue'
import UserInfo from './components/initial/UserInfo.vue'
import UserDevice from './components/initial/UserDevice.vue'
import "./style.css"

const usersLoc = ref([
  { label: "IP Address", value: "10.37.196.70" },
  { label: "City", value: "Provo" },
  { label: "Region", value: "Utah" },
  { label: 'ZIP', value: '84606' },
  { label: 'Country', value: 'United States' },
])

const usersInfo = ref([
  { label: 'School', value: 'Brigham Young University' },
  { label: 'Name', value: 'John Doe' },
  { label: 'Phone Number', value: '(555) 555-5555' },
  { label: 'Email', value: 'X5k6Z@example.com' },
])

const usersDevice = ref([
  { label: 'Password', value: '********' },
  { label: 'Username', value: 'johndoe' },
])

</script>
