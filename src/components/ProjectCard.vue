<template>
  <div class="card" @click="openLink">
    <h3 class="card-title">{{ title }}</h3>
    <img :src="image" alt="Project Image" class="card-image" />
    <p class="card-description">{{ description }}</p>
    <p class="technologies-used">{{ technologiesUsed }}</p>
  </div>
</template>

<script>
export default {
  name: 'ProjectCard',
  props: {
    title: {
      type: String,
      required: true
    },
    image: {
      type: String,
      required: true
    },
    description: {
      type: String,
      required: true
    },
    technologies: {
      type: Array,
      required: true
    },
    link: {
      type: String,
      required: true
    }
  },
  computed: {
    technologiesUsed() {
      return this.technologies.join(', ');
    }
  },
  methods: { // CHANGED: Added methods section
    openLink() { // CHANGED: Added openLink method
      window.open(this.link, '_blank'); // CHANGED: Opens link in new tab
    } // CHANGED: End of openLink method
  } // CHANGED: End of methods section
}
</script>

<style scoped>
.card {
  border-radius: 8px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  margin: 20px;
  padding: 10px 20px;
  width: 350px;
  height: 550px;
  text-align: left;
  background-color: white;
  display: flex;
  flex-direction: column;
  justify-content: start;
  cursor: pointer;
  /* CHANGED: Added cursor pointer for better UX */
}

.card:hover {
  /* CHANGED: Added hover effect */
  box-shadow: 0 6px 12px rgba(0, 0, 0, 0.15);
  /* CHANGED: Enhanced shadow on hover */
  transform: translateY(-2px);
  /* CHANGED: Subtle lift effect */
  transition: all 0.3s ease;
  /* CHANGED: Smooth transition */
}

/* CHANGED: End of hover effect */


.card-image {
  width: 100%;
  height: 200px;
  border-radius: 8px;
  object-fit: contain;
  /* Shows full image, may have letterboxing */
  background: #f0f0f0;
  /* Background color for empty areas */
}

.card-title {
  font-size: 1.5em;
  margin: 10px 0;
}

.card-description {
  font-size: 1em;
  color: #666;
  overflow: hidden;
  text-overflow: ellipsis;
  display: -webkit-box;
  -webkit-line-clamp: 12;
  -webkit-box-orient: vertical;
}

.technologies-used {
  margin-top: auto;
  font-size: 0.9em;
  font-weight: bold;
  background-color: transparent;
  color: #BB4430;
}

@media (max-width: 768px) {
  .card {
    margin: 5px;
    padding: 10px;
    width: calc(100% - 40px);
    height: auto;
  }

  .card-description {
    -webkit-line-clamp: 20;
  }
}
</style>