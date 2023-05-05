<script>
import Views from './components/Views.vue'
export default {
  components: {
    Views
  }
}
</script>

<template>
  <div class="main">
    <Views />

  </div>
</template>

<style scoped>
.main {
  width: 100vw;
  height: 100vh;
  background-color: rgb(183, 226, 237);
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
