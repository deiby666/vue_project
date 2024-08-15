<template>
  <div class="teams-container">
    <h2>Teams:</h2>
    <div class="cards">
      <div v-for="team in teams" :key="team.name" class="card">
        <h3>{{ team.name }}</h3>
        <p>{{ team.description }}</p>
        <ul>
          <li v-for="participant in team.participants" :key="participant">{{ participant }}</li>
        </ul>
        <input v-model="team.newMember" placeholder="Enter member name" />
        <button @click="addMember(team)">Add Member</button>
      </div>
    </div>
  </div>
</template>

<script lang="ts" setup>
import { ref } from 'vue';

const teams = ref([
  {
    name: "Team Alpha",
    description: "This is a description for Team Alpha.",
    participants: ["Alice", "Bob", "Charlie"],
    newMember: '' 
  },
  {
    name: "Team Beta",
    description: "This is a description for Team Beta.",
    participants: ["David", "Eve", "Frank"],
    newMember: '' 
  },
  {
    name: "Team Gamma",
    description: "This is a description for Team Gamma.",
    participants: ["Grace", "Heidi", "Ivan"],
    newMember: '' 
  }
]);

const addMember = (team:any) => {
  if (team.newMember.trim()) {
    team.participants.push(team.newMember.trim());
    team.newMember = ''; 
  }
};
</script>

<style scoped lang="scss">
.teams-container {
  padding: 20px;
}

.cards {
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
}

.card {
  border: 1px solid #ddd;
  border-radius: 8px;
  padding: 15px;
  width: 300px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

.card h3 {
  margin-top: 0;
}

.card ul {
  list-style: none;
  padding-left: 0;
}

.card li {
  margin: 5px 0;
}

.card input {
  margin-right: 10px;
  padding: 5px;
}

.card button {
  background-color: #007bff;
  color: white;
  border: none;
  border-radius: 5px;
  padding: 5px 10px;
  cursor: pointer;
}

.card button:hover {
  background-color: #0056b3;
}
</style>
