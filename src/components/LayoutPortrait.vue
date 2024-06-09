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
    border: solid;
    border-color: rgb(255, 255, 255);
    border-width: 8px;
    border-radius: 225px;
    overflow: hidden;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  
  .image {
    width: 100%;
    height: 100%;
    object-fit: cover;
  }
</style>
  