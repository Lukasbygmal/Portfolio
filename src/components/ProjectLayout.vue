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
import mountain from '@/assets/mountain.jpeg';

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
          title: 'Project One',
          image: mountain,
          description: "This project involved creating a dynamic portfolio website using Vue.js, focusing on a modern interface, smooth navigation, and interactive features such as a project gallery and contact form. It integrates a headless CMS for content management, ensuring responsiveness across devices. The result is a high-performance website demonstrating proficiency in building engaging web applications. word word word word word word word word word word word word word word word word",
          technologies: ['Vue.js', 'JavaScript', 'CSS']
        },
        {
          id: 2,
          title: 'Project Two',
          image: mountain,
          description: 'This is a description for project two.',
          technologies: ['React', 'JavaScript', 'HTML']
        },
        {
          id: 3,
          title: 'Project Three',
          image: mountain,
          description: 'This is a description for project three.',
          technologies: ['Angular', 'TypeScript', 'SCSS']
        },
        {
          id: 4,
          title: 'Project Four',
          image: mountain,
          description: 'This is a description for project four.',
          technologies: ['Node.js', 'Express', 'MongoDB']
        },
        {
          id: 5,
          title: 'Project Five',
          image: mountain,
          description: 'This is a description for project five.',
          technologies: ['Python', 'Django', 'PostgreSQL']
        },
        {
          id: 6,
          title: 'Project Six',
          image: mountain,
          description: 'This is a description for project six.',
          technologies: ['Ruby on Rails', 'Ruby', 'SQLite']
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
