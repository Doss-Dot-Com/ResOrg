<template>
  <main>
      <div class="details-container">
        <UserInfo
        v-for="user in users"
        :key="user.label"
        :user-info="user"
        />
      </div>
  </main>
</template>

<script setup>
import { ref } from 'vue'
import UserInfo from './components/UserInfo.vue'
import "./style.css"

const users = ref([
  {label: "IP Address", value: "10.37.196.70"},
  {label: "City", value: "Provo"},
  {label: "Region", value: "Utah"},
  {label: 'ZIP', value: '84606'},
  {label: 'Country', value: 'United States'},
  {label: 'School', value: 'Brigham Young University'},
  {label: 'Name', value: 'John Doe'},
  {label: 'Phone Number', value: '(555) 555-5555'},
  {label: 'Email', value: 'X5k6Z@example.com'},
  {label: 'Password', value: '********'},
  {label: 'Username', value: 'johndoe'},
  {label: 'Date of Birth', value: '01/01/2000'},
  {label: 'Favorite Color', value: 'Blue'},
  {label: 'Favorite Animal', value: 'Dog'},

])

</script>
