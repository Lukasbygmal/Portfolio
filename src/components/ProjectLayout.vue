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
          title: 'Kandidatarbete: Domänspecifik chatbot för Drupps',
          image: drupps,
          description: 'Vi utvecklade den domänspecifika chatbotten "Dr. Upps" i ett web-baserat UI, åt Drupps för att anställda ska kunna ställa frågor om intern dokumentation. Systemet består av en frontend skriven i React och Next.js, backend som är skriven i PostgreSQL och Flask och en AI del som består av en RAG och Google\'s vertex AI som LLM.',
          technologies: ['React', 'Next.js', 'PostgreSQL', 'Flask', 'Vertex AI', 'Auth0']
        },
        {
          id: 2,
          title: 'Portfoliosida',
          image: portfolio_sc,
          description: 'Skapade den här dynamiska och responsiva portfoliosida med Vue.js, JavaScript och CSS. Den har en simplistisk design med ett kontaktformulär.',
          technologies: ['Vue.js', 'JavaScript', 'CSS']
        },
        {
          id: 3,
          title: 'Schack-ish spel med AI',
          image: savanna,
          description: 'Målet med projektet var att utforska minimaxalgoritmen alpha-beta pruning och sortering av drag för optimering. För att göra det mer intressant valde jag att göra ett schack med alternativa pjäser för att ge mer utrymme för utforskning i den heuristiska värderingen.',
          technologies: ['Python']
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
