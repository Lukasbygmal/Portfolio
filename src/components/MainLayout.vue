<template>
  <div class="main-container">
    <h1>Lukas Bygdell Malmstig</h1>
    <div>
      <LayoutPortrait></LayoutPortrait>
    </div>
    <div>
      <LayoutDescription></LayoutDescription>
    </div>
    <div>
      <layout-button buttonText="Me" link="https://example.com/button1"></layout-button>
      <layout-button buttonText="Projects" link="https://example.com/button2"></layout-button>
      <layout-button buttonText="CV" link="/LukasBygdellMalmstig-CV.pdf"></layout-button>
      <layout-button buttonText="Contact" link="https://example.com/button3"></layout-button>
    </div>
  </div>
</template>

<script>
import LayoutButton from './LayoutButton.vue';
import LayoutPortrait from './LayoutPortrait.vue';
import LayoutDescription from './LayoutDescription.vue';

export default {
  name: 'MainLayout',
  components: {
    LayoutPortrait,
    LayoutButton,
    LayoutDescription,
  }
}
</script>


<style scoped>

h1 {
  margin: 0;
  padding: 4px;
  font-size: 72px;
}

.main-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  justify-content: center;
}
</style>
