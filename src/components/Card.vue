<script setup lang="ts">
export interface Artwork {
  id: number;
  title: string;
  description: string;
  artistName: string;
  artistProfile: string;
  image: string;
  cost: number;
  currency: string;
  daysLeft: number;
}

defineProps<Artwork>()
</script>

<template>
  <div class="card">
    <div class="artwork">
      <img :src="image" alt="nft artwork">
    </div>

    <h3 class="title">{{ title }} #{{ id }}</h3>
    <p class="description">{{ description }}</p>

    <div class="numbers">
      <h6 class="currency"><img src="/icon-ethereum.svg" alt="currency symbol"> {{ cost }} {{ currency }}</h6>
      <h6 class="expiry"><img src="/icon-clock.svg" alt="clock"> {{ daysLeft }} {{ daysLeft > 1 ? "days" : "day" }} left
      </h6>
    </div>

    <div class="line" />

    <div class="artist-details">
      <div class="profile-photo">
        <img :src="artistProfile" alt="artistName">
      </div>
      <p><span>Creation of</span> <span class="name">{{ artistName }}</span></p>
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
