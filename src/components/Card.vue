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
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  gap: 1rem;
  width: 100%;
  max-width: 350px;
  color: var(--white);
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

.title {
  color: inherit;
  font-weight: 600;
  font-size: 1.5rem;
  letter-spacing: 1px;
}

.description {
  color: var(--soft-blue);
  font-size: 18px;
  font-weight: 300;
  line-height: 25px;
}

.numbers {
  display: flex;
  justify-content: space-between;

  .currency,
  .expiry {
    display: flex;
    align-items: center;
    gap: 0.5rem;
  }

  .currency {
    color: var(--cyan);
    font-weight: 600;
  }

  .expiry {
    color: var(--soft-blue);
    font-weight: 300;
  }
}

.line {
  height: 1px;
  width: 100%;
  background: var(--line-color);
}

.artist-details {
  display: flex;
  justify-content: start;
  align-items: center;
  gap: 1rem;

  .profile-photo {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 2rem;
    aspect-ratio: 1/1;
    border: 1px solid var(--white);
    border-radius: 100%;

    img {
      width: 100%;
    }
  }

  span {
    color: var(--soft-blue);
    font-weight: 300;

    &.name {
      color: white;
    }
  }
}
</style>
