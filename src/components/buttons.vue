<template>
    <div class="buttons">
      <button
        :class="{ active: activeTab === 'profile' }"
        @click="changeTab('profile')"
      >
        <i class="fa-solid fa-user"></i> Profile
      </button>
      <button
        :class="{ active: activeTab === 'team' }"
        @click="changeTab('team')"
      >
        <i class="fa-solid fa-users"></i> Team
      </button>
      <button
        :class="{ active: activeTab === 'connections' }"
        @click="changeTab('connections')"
      >
        <i class="fa-solid fa-link"></i> Connections
      </button>
      <button
        :class="{ active: activeTab === 'projects' }"
        @click="changeTab('projects')"
      >
        <i class="fa-solid fa-diagram-project"></i> Projects
      </button>
    </div>
  </template>
  
  <script lang="ts" setup>
  
  const props = defineProps({
    activeTab: String
  });
  
  const emit = defineEmits(['changeContent']);
  
  const changeTab = (tab: string) => {
    emit('changeContent', tab);
  };
  </script>
  
  <style scoped lang="scss">
  .buttons {
    display: flex;
    gap: 10px;
    margin-top: 20px;
  }
  
  .buttons button {
    background-color: aqua;
    border-radius: 10px;
    padding: 5px;
    cursor: pointer;
    border: none;
  }
  
  .buttons button.active {
    background-color: blue;
  }
  </style>
