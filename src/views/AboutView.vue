<script setup>
import axios from 'axios';
import { ref, onMounted } from 'vue';

const data = ref([]);

onMounted(async () => {
  const resp = await axios.get("http://hello-developer-sandbox-andrepaulinobtw-dev.apps.rm1.0a51.p1.openshiftapps.com/movies");
  data.value = resp.data;
})

</script>

<template>
  <div class="about">
    <h1>This is an about page</h1>
    <p v-for="item in data">{{ item.title }}</p>
  </div>
</template>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
