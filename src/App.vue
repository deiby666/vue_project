<template>
  <search />
  <profile />
  <buttons @changeContent="changeContent" :activeTab="activeTab" />
  <div class="profile-information" v-if="activeTab === 'profile'"> 
    <div class="info">
      <about />
      <overview />
    </div>
    <div class="user-details">
      <projects />
      <div class="connection-teams">
        <connections />
        <teams />
      </div>
    </div>
  </div>
  <TeamComponent v-if="activeTab === 'team'" /> 
  <connectionComponent v-if="activeTab === 'connections'" /> 
  <projectsComponent v-if="activeTab === 'projects'" /> 
  
</template>

<script lang="ts" setup>
import profile from "@/components/profile.vue";
import about from "@/components/about.vue";
import overview from "@/components/overview.vue";
import projects from "@/components/projects.vue";
import search from "@/components/search.vue";
import connections from "@/components/connections.vue";
import teams from "@/components/teams.vue";
import buttons from "./components/buttons.vue";
import { onMounted } from "vue";
import { ref } from "vue";
import TeamComponent from "./components/changing/team-component.vue";
import connectionComponent from "./components/changing/connections-component.vue";
import projectsComponent from "./components/changing/projects-component.vue";

const activeTab = ref("profile");

const changeContent = (tab: string) => {
  activeTab.value = tab;
};

</script>

<style>
.profile-information {
  display: flex;
  margin-top: 40px;
  gap: 20px;
  width: 100%;
}

.user-details {
  display: flex;
  flex-direction: column;
  width: 70%;
  gap: 20px;
}

.info {
  width: 30%;
  display: flex;
  flex-direction: column;
  gap: 15px;
}

.connection-teams {
  display: flex;
  gap: 20px;
}

@media (max-width: 800px){
  .profile-information {
    flex-wrap: wrap;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}

.user-details {
  display: flex;
  flex-direction: column;
  width: 100%;
  gap: 20px;
}

.info {
  width: 50%;
  display: flex;
  flex-direction: column;
  gap: 15px;
}

.connection-teams {
  display: flex;
  gap: 20px;
}
}
</style>
