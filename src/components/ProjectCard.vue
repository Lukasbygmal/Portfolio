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
  methods: {
    openLink() {
      window.open(this.link, '_blank');
    }
  }
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
}

.card:hover {
  box-shadow: 0 6px 12px rgba(0, 0, 0, 0.15);
  transform: translateY(-2px);
  transition: all 0.3s ease;
}


.card-image {
  width: 100%;
  height: 200px;
  border-radius: 8px;
  object-fit: contain;
  background: #f0f0f0;
}

.card-title {
  font-size: 1.5em;
  margin: 10px 0;
}

.card-description {
  font-size: 1.1em;
  color: #666;
  overflow: hidden;
  text-overflow: ellipsis;
  display: -webkit-box;
  -webkit-line-clamp: 12;
  -webkit-box-orient: vertical;
}

.technologies-used {
  margin-top: auto;
  font-size: 1.2em;
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
    font-size: 1em;
  }
}
</style>