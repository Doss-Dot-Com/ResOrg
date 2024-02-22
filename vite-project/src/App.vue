<template>
  <main>
    <div class="details-container">
      <UserLoc v-for="(userLoc, index) in usersLoc" :key="index" :usersLoc="userLoc" :showValue="index <= currentLocIndex"
        :index="index" :completed="userLoc.showCompleted" />
      <LoadSpinner v-if="showSpinner"/>
      <UserInfo v-if="showInfo" v-for="(userInfo, index) in usersInfo" :key="index" :usersInfo="userInfo"
        :showValue="index <= currentInfoIndex" :index="index" :completed="userInfo.showCompleted" />
        <LoadSpinner v-if="showSpinner2"/>
      <UserDevice v-if="showDevice" v-for="(userDevice, index) in usersDevice" :key="index" :usersDevice="userDevice"
        :showValue="index <= currentDeviceIndex" :index="index" :completed="userDevice.showCompleted" />
      <br>
      <span class="qrcode">
        <VueQRCode value="Would you risk your information?" :options=" { color: { dark: '#00d1d1', light: '#03001111' } }"/>
      </span>

    </div>
  </main>
</template>

<script setup>
import { ref, onMounted } from 'vue'
import UserLoc from './components/initial/UserLoc.vue'
import UserInfo from './components/initial/UserInfo.vue'
import UserDevice from './components/initial/UserDevice.vue'
import "./style.css"
import LoadSpinner from './components/elements/LoadSpinner.vue'
import VueQRCode from '@chenfengyuan/vue-qrcode';


const usersLoc = ref([
  { label: "IP Address", value: "10.37.196.70", showCompleted: false },
  { label: "City", value: "Provo", showCompleted: false },
  { label: "Region", value: "Utah", showCompleted: false },
  { label: 'ZIP', value: '84606', showCompleted: false },
  { label: 'Country', value: 'United States', showCompleted: false },
])

const usersInfo = ref([
  { label: 'School', value: 'Brigham Young University', showCompleted: false },
  { label: 'Name', value: 'John Doe', showCompleted: false },
  { label: 'Phone Number', value: '(555) 555-5555', showCompleted: false },
  { label: 'Email', value: 'X5k6Z@example.com', showCompleted: false },
])

const usersDevice = ref([
  { label: 'Password', value: '********' },
  { label: 'Username', value: 'johndoe' },
])

const currentLocIndex = ref(-1);
const currentInfoIndex = ref(-1);
const currentDeviceIndex = ref(-1);

const showInfo = ref(false)
const showDevice = ref(false)
const showSpinner = ref(false)
const showSpinner2 = ref(false)

onMounted(() => {
  const intervalLocId = setInterval(() => {
    currentLocIndex.value += 1;
    if (currentLocIndex.value > usersLoc.value.length - 1) {
      clearInterval(intervalLocId);
    } else {
      usersLoc.value[currentLocIndex.value].showCompleted = true;
    }
  }, 300)
  setTimeout(() => {
    showSpinner.value = true;
  }, 1570)
  setTimeout(() => {
    showSpinner.value = false;
    showInfo.value = true
    const intervalInfoId = setInterval(() => {
      currentInfoIndex.value += 1;
      if (currentInfoIndex.value > usersInfo.value.length - 1) {
        clearInterval(intervalInfoId);
      } else {
        usersInfo.value[currentInfoIndex.value].showCompleted = true;
      }
      setTimeout(() => {
        showSpinner2.value = true;
      }, 930)

      setTimeout(() => {
        showSpinner2.value = false
        showDevice.value = true
        const intervalDeviceId = setInterval(() => {
          currentDeviceIndex.value += 1;
          if (currentDeviceIndex.value > usersDevice.value.length - 1) {
            clearInterval(intervalDeviceId);
          } else {
            usersDevice.value[currentDeviceIndex.value].showCompleted = true;
          }
        }, 2100)  
      }, 2500)
    }, 300)
  }, 2500)
});
</script>