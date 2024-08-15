<template>
    <div class="projects">
      <h2>Projects:</h2>
      <div class="cards">
        <!-- Itera sobre el array de proyectos para crear tarjetas -->
        <div v-for="project in projects" :key="project.name" class="card">
          <h3>{{ project.name }}</h3>
          <p><i class="fa-solid fa-info-circle"></i> {{ project.description }}</p>
          <p><i class="fa-solid fa-calendar-days"></i> {{ project.date }}</p>
          <!-- Botón para editar -->
          <button @click="editProject(project.name)" class="edit-button">
            Edit
          </button>
        </div>
      </div>
    </div>
  </template>
  
  <script lang="ts" setup>
  import { ref } from 'vue';
  
  // Define un array de proyectos
  const projects = ref([
    {
      name: "Project Alpha",
      description: "Developed a comprehensive application for task management.",
      date: "March 2023"
    },
    {
      name: "Project Beta",
      description: "Worked on a collaborative platform for remote teams.",
      date: "July 2023"
    },
    {
      name: "Project Gamma",
      description: "Contributed to an e-commerce website redesign.",
      date: "December 2023"
    }
  ]);
  
  // Función para manejar la edición de proyectos
  const editProject = (name: string) => {
    // Aquí puedes implementar la lógica para editar el proyecto
    // Por ejemplo, abrir un formulario de edición o mostrar un modal
    console.log(`Edit project: ${name}`);
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
    width: 250px; /* Ajusta el tamaño de las tarjetas */
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    position: relative;
  }
  
  .card h3 {
    margin-top: 0;
  }
  
  .card p {
    margin: 5px 0;
  }
  
  .edit-button {
    background-color: blue;
    color: white;
    border: none;
    border-radius: 5px;
    padding: 5px 10px;
    cursor: pointer;
    position: absolute;
    bottom: 15px;
    right: 15px;
  }
  </style>
  