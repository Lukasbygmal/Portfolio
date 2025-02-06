<template>
  <div class="main-container">
    <div class="content-container">
      <ProjectCard 
        v-for="project in projects" 
        :key="project.id" 
        :title="project.title" 
        :image="project.image" 
        :description="project.description" 
        :technologies="project.technologies"
      />
    </div>
  </div>
</template>

<script>
import ProjectCard from './ProjectCard.vue';
//import mountain from '@/assets/mountain.jpeg';
import savanna from '@/assets/savanna.png';
import portfolio_sc from '@/assets/portfolio_sc.png';
import drupps from '@/assets/drupps.png';
import teamTumble from '@/assets/TeamTumble.png';

export default {
  name: 'ProjectLayout',
  components: {
    ProjectCard
  },
  data() {
    return {
      projects: [
        {
          id: 1,
          title: 'Bachelor´s Thesis: Domain Specific Chatbot for Drupps',
          image: drupps,
          description: 'We developed the domain-specific chatbot Dr. Upps in a web-based UI for Drupps, enabling employees to ask questions about internal documentation. The system consists of a frontend built with React and Next.js, a backend implemented with PostgreSQL and Flask, and an AI component comprising a RAG and Google´s Vertex AI as the LLM.',
          technologies: ['React', 'Next.js', 'PostgreSQL', 'Flask', 'Vertex AI', 'Auth0']
        },
        {
          id: 2,
          title: 'Portfolio Site',
          image: portfolio_sc,
          description: 'Created a dynamic and responsive portfolio site using Vue.js, JAvascript and CSS. It has a simplistic design showcasing my projects and working contact form.',
          technologies: ['Vue.js', 'JavaScript', 'CSS']
        },
        {
          id: 3,
          title: 'Savanna Stratgey: Chess-ish Game with AI',
          image: savanna,
          description: 'The game features unique piece movements distinct from chess, although with similar strategic elements. The goal of the project was to explore the implementation of the minimax algorithm with alpha-beta pruning, optimizing it through move ordering and heuristic evaluation techniques.',
          technologies: ['Python']
        },
        {
          id: 4,
          title: 'TeamTumbler: Team Randomizer',
          image: teamTumble,
          description: 'TeamTumble is an interactive web application I developed that uses a Galton board physics simulation to randomly generate teams. The site provides a fun and functional way to sort groups, using matter.js. It is avialable at Teamtumble.net.',
          technologies: ['Vue.js, TypeScript, Matter.js']
        },
      ]
    };
  }
}
</script>

<style scoped>
.main-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  justify-content: center;
  min-height: 100vh;
  background-color: #1AD9E5;
}

.content-container {
  display: flex;
  align-items: center;
  justify-content: center;
  margin-top: 20px; 
  flex-wrap: wrap;
}

@media (max-width: 768px) {
  .content-container {
    flex-direction: column;
  }
}
</style>
