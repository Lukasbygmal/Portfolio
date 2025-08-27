<template>
  <div class="main-container">
    <div class="content-container">
      <ProjectCard v-for="project in projects" :key="project.id" :title="project.title" :image="project.image"
        :description="project.description" :technologies="project.technologies" :link="project.link" />
    </div>
  </div>
</template>

<script>
import ProjectCard from './ProjectCard.vue';
//import mountain from '@/assets/mountain.jpeg';
import savanna from '@/assets/savanna.png';
import portfolio_sc from '@/assets/portfolio_sc.png';
import drupps from '@/assets/drupps.png';
import teamTumble from '@/assets/teamTumble.png';
import ariadne from '@/assets/ariadne.png';
import neatArcade from '@/assets/neat_arcade.png';

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
          technologies: ['React', 'Next.js', 'PostgreSQL', 'Flask', 'Vertex AI', 'Auth0'],
          link: "/KandidatArbete.pdf"
        },
        {
          id: 2,
          title: 'Wake of Ariadne',
          image: ariadne,
          description: 'A retro-inspired dungeon crawler rpg, with speedtyping as combat. The game is built in C++, with a database in PostgreSQL and a Flask REST API. Additionally, it uses OAuth with github. Published at itch.io!',
          technologies: ['C++', 'Flask', 'Python', 'PostgreSQL', 'Make', 'OpenSSL', 'SFML', 'OAuth'],
          link: "https://lukasbygmal.itch.io/wake-of-ariadne"
        },
        {
          id: 3,
          title: 'TeamTumbler: Team Randomizer',
          image: teamTumble,
          description: 'TeamTumble is an interactive web application I developed that uses a Galton board physics simulation to randomly generate teams. The site provides a fun and functional way to sort groups, using matter.js. It is live!',
          technologies: ['Vue.js', 'TypeScript', 'Matter.js'],
          link: "https://teamtumble.net/"
        },
        {
          id: 4,
          title: 'NEAT Arcade: (work in progress)',
          image: neatArcade,
          description: 'Collection of arcade games allowing for simulation of NeuroEvolution of Augmenting Topologies, evolution based AI. ',
          technologies: ['Python', 'NEAT'],
          link: "https://github.com/Lukasbygmal/NEAT-arcade"
        },
        {
          id: 5,
          title: 'Savanna Stratgey: Chess-ish Game with AI',
          image: savanna,
          description: 'The game features unique piece movements distinct from chess, although with similar strategic elements. The goal of the project was to explore the implementation of the minimax algorithm with alpha-beta pruning, optimizing it through move ordering and heuristic evaluation techniques.',
          technologies: ['Python'],
          link: "https://github.com/Lukasbygmal/Savanna_Strategy"
        },
        {
          id: 6,
          title: 'Portfolio Site',
          image: portfolio_sc,
          description: 'Created a dynamic and responsive portfolio site using Vue.js, Javascript and CSS. It has a simplistic design showcasing my projects and a working contact form.',
          technologies: ['Vue.js', 'JavaScript', 'CSS'],
          link: "https://github.com/Lukasbygmal/Portfolio"
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
