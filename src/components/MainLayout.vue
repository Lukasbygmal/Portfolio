<template>
  <div class="main-container">
    <div class="content-container">
      <LayoutPortrait></LayoutPortrait>
      <LayoutDescription></LayoutDescription>
    </div>
    <div class="social-buttons-container">
      <SocialButton url="https://github.com/lukasbygmal" image="/github.png" />
      <SocialButton url="https://www.linkedin.com/in/lukas-bygdell-malmstig-14212a2a2/" image="/linkedinB.png" />
    </div>
  </div>
</template>

<script>
import LayoutPortrait from './LayoutPortrait.vue';
import LayoutDescription from './LayoutDescription.vue';
import SocialButton from './SocialButton.vue';

export default {
  name: 'MainLayout',
  components: {
    LayoutPortrait,
    LayoutDescription,
    SocialButton,
  },
};
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

.social-buttons-container {
  display: flex;
  gap: 15px;
  margin-top: 20px;
}

@media (max-width: 768px) {
  .content-container {
    flex-direction: column;
  }

  .social-buttons-container {
    flex-wrap: wrap;
    justify-content: center;
  }
}
</style>
