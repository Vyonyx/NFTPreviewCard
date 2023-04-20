<script setup lang="ts">
</script>

<template>
  <div class="card">
    <div class="artwork">
      <img src="../assets/image-equilibrium.jpg" alt="nft artwork">
    </div>
  </div>
</template>

<style lang="scss" scoped>
.card {
  width: 100%;
  max-width: 320px;
  background: var(--card-bg);
  aspect-ratio: 1/1.7;
  border-radius: 1rem;
  box-shadow: 0px 0px 20px 10px hsla(0, 0, 0, 0.1);
  padding: 1.5rem;
}

.artwork {
  width: 100%;
  aspect-ratio: 1/1;
  border-radius: 0.5rem;
  display: flex;
  justify-content: center;
  align-items: center;
  overflow: hidden;

  img {
    width: 100%;
  }
}
</style>
