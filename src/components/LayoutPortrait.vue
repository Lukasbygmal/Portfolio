<template>
  <div class="layout-portrait">
    <img :src="imageSrc" alt="Portrait Image" class="image">
  </div>
</template>

<script>
export default {
  name: 'LayoutPortrait',
  data() {
    return {
      imageSrc: require('@/assets/port.jpeg')
    }
  }
}
</script>

<style scoped>
.layout-portrait {
  width: 225px;
  height: 225px;
  overflow: hidden;
  display: flex;
  justify-content: center;
  align-items: center;
  clip-path: circle(50%);
  margin: 20px;
}

.image {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

@media (max-width: 768px) {
  .layout-portrait {
    width: 125px;
    height: 125px;
    margin-top: 80px;
  }
}
</style>
