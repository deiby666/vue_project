<template>
  <div class="connections">
    <h2>Connections:</h2>
    <div class="cards">
      <div v-for="connection in connections" :key="connection.name" class="card">
        <h3>{{ connection.name }}</h3>
        <p><i class="fa-solid fa-map-pin"></i> {{ connection.location }}</p>
        <p><i class="fa-solid fa-briefcase"></i> {{ connection.role }}</p>
        <button @click="disconnect(connection.name)" class="disconnect-button">
          Disconnect
        </button>
      </div>
    </div>
  </div>
</template>

<script lang="ts" setup>
import { ref } from 'vue';

// Define un array de personas conectadas
const connections = ref([
  {
    name: "John Doe",
    location: "New York",
    role: "Software Engineer"
  },
  {
    name: "Jane Smith",
    location: "San Francisco",
    role: "Product Manager"
  },
  {
    name: "Alice Johnson",
    location: "Chicago",
    role: "UX Designer"
  }
]);

// Función para manejar la desconexión
const disconnect = (name: string) => {
  console.log(`Disconnected from ${name}`);
  connections.value = connections.value.filter(connection => connection.name !== name);
};
</script>

<style scoped lang="scss">

.cards {
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
}

.card {
  border: 1px solid #ddd;
  border-radius: 8px;
  padding: 15px;
  width: 250px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  position: relative;
}

.card h3 {
  margin-top: 0;
}

.card p {
  margin: 5px 0;
}

.disconnect-button {
  background-color: red;
  color: white;
  border: none;
  border-radius: 5px;
  padding: 5px 10px;
  cursor: pointer;
}
</style>
