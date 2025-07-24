<template>
  <a :href="link" class="layout-button">{{ buttonText }}</a>
</template>

<script>
export default {
  name: 'LayoutButton',
  props: {
    buttonText: {
      type: String,
      required: true
    },
    link: {
      type: String,
      required: true
    }
  }
}
</script>

<style>
.layout-button {
  background-color: white;
  color: black;
  border: none;
  border-radius: 5px;
  padding: 15px 30px;
  font-size: 16px;
  cursor: pointer;
  text-decoration: none;
  display: inline-block;
  margin: 10px;
  width: 200px;
  text-align: center;
}

.layout-button:hover {
  background-color: #f0f0f0;
}
</style>