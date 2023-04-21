<script setup lang="ts">
import Card from './components/Card.vue'
import type { Artwork } from './components/Card.vue';

const artworks: Artwork[] = [
  {
    id: 3429,
    title: "Equilibrium",
    description: "Our Equilibrium collection promotes balance and calm.",
    artistName: "Jules Wyvern",
    artistProfile: "/image-avatar.png",
    image: "/image-equilibrium.jpg",
    cost: 0.041,
    currency: "ETH",
    daysLeft: 3,
  },
]
</script>

<template>
  <main>
    <Card v-for="({ id, title, description, artistName, artistProfile, image, cost, currency, daysLeft }) in artworks"
      :key="id" :id="id" :title="title" :description="description" :artist-name="artistName"
      :artist-profile="artistProfile" :image="image" :cost="cost" :currency="currency" :days-left="daysLeft" />
  </main>
</template>

<style lang="scss" scoped>
main {
  background: var(--main-bg);
  padding: 2rem;
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100vh;
}
</style>

