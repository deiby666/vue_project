<template>
  <header>
    <div class="header-background"></div>
    <div class="profile">
      <img :src="profileImage" alt="" class="w-10" style="border: black solid 2px" />
      
      <div class="profile-data">
        <h2>{{ name }}</h2>
        <div class="moreInfo">
          <p><i class="fa-solid fa-code"></i> {{ occupation }}</p>
          <p><i class="fa-solid fa-map-pin"></i> {{ location }}</p>
          <p><i class="fa-solid fa-calendar-days"></i> {{ joinDate }}</p>
        </div>
      </div>
    </div>
    
    <button><i class="fa-solid fa-check"></i> {{ connectionStatus }}</button>
  </header>
</template>

<script lang="ts" setup>
import { ref } from 'vue'; 

import profileImagePath from '@/assets/images/what-is-the-source-of-this-cool-photo-of-haerin-v0-t2riizouutob1 (1).jpg'

const profileImage = ref(profileImagePath); 
const name = ref("Kang Haerin");
const occupation = ref("Coder");
const location = ref("Medellin");
const joinDate = ref("Joined April 2021");
const connectionStatus = ref("Connected");
</script>

<style scoped lang="scss">
header {
  position: relative;
  height: 250px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 20px;
  background-color: white;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  border-bottom-left-radius: 10px;
  border-bottom-right-radius: 10px;
}

.header-background {
  background-image: url("../assets/images/background-2435915_1280.jpg");
  background-size: cover;
  background-repeat: no-repeat;
  width: 100%;
  height: 40%;
  position: absolute;
  top: 0;
  left: 0;
}

.profile {
  display: flex;
  align-items: center;
  margin-top: 20px;
  gap: 13px;
  z-index: 1;
}

.moreInfo {
  margin-top: 10px;
  display: flex;
  gap: 20px;
}

header button {
  background-color: aqua;
  border-radius: 10px;
  padding: 5px;
  cursor: pointer;
  position: absolute;
  bottom: 0;
  right: 0;
  margin: 20px;
}

@media (max-width: 800px){
  header {
    width: 100%;
}

  .profile img{
    width: 20% !important;
  }
}
</style>
