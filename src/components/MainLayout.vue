<template>
  <div class="main-container">
    <div class="content-container">
      <LayoutPortrait></LayoutPortrait>
      <LayoutDescription></LayoutDescription>
    </div>
  </div>
</template>

<script>
import LayoutPortrait from './LayoutPortrait.vue';
import LayoutDescription from './LayoutDescription.vue';

export default {
  name: 'MainLayout',
  components: {
    LayoutPortrait,
    LayoutDescription,
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
  background-color: #F3DFA2;
}

.content-container {
  display: flex;
  align-items: center;
  justify-content: center;
  margin-top: 20px; 
  flex-wrap: wrap;
}

@media (max-width: 768px) {
  
}

</style>
