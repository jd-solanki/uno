<script setup>
import { ref } from 'vue';

const icon = ref('')


// You can create a fake API at: https://mocki.io/fake-json-api
// API response: { icon: 'i-mdi-<icon-name>' }
fetch('https://mocki.io/v1/8ee750ba-6e3f-480e-9579-a08448271144').then(res => res.json()).then(data => {
  console.log(data.icon)
  icon.value = data.icon
});
</script>

<template>
  <p>Icon: {{ icon }}</p>
  <div class="i-mdi-account"></div>
  <div :class="icon"></div>
</template>