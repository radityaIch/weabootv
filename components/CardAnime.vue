<script setup lang="ts">
defineProps({
  mal_id: { type: Number, default: 0 },
  episodes: { type: Number, default: 0 },
  title: { type: String, default: "" },
  image: { type: String, default: "" },
});
</script>

<template>
  <NuxtLink :to="`/detail/${mal_id}`" class="item-list">
    <div class="image-container">
      <img :src="image" :alt="title" class="item-image" />
    </div>
    <p class="item-episodes">{{ episodes }} episodes</p>
    <p class="item-title">
      {{ title }}
    </p>
  </NuxtLink>
</template>

<style lang="scss" scoped>
.item-list {
  border-radius: 8px;
  box-shadow: 1px 2px 15px rgb(0 0 0 / 15%);
  margin-bottom: 30px;
  margin-right: 1.8%;
  overflow: hidden;
  position: relative;
  width: 18.5%;

  &:nth-child(5n) {
    margin-right: 0;
  }

  @media screen and (max-width: 1180px) {
    width: 22.5%;
  }

  @media screen and (max-width: 760px) {
    width: 45.5%;
  }

  @media screen and (max-width: 375px) {
    width: 88.5%;
  }
}
.image-container {
  height: 0;
  padding-top: 100%;
  position: relative;
}
.item-image {
  height: 100%;
  left: 0;
  object-fit: cover;
  position: absolute;
  top: 0;
  width: 100%;
}

.item-episodes {
  background-color: #004269;
  border-radius: 4px;
  color: #fff;
  left: 0;
  position: absolute;
  padding: 4px;
  text-align: center;
  top: 0;
  width: auto;
}
.item-title {
  background-color: rgba(17, 17, 17, 0.63);
  bottom: 0;
  color: #fff;
  left: 0;
  padding: 5px 0;
  position: absolute;
  text-align: center;
  width: 100%;
}
</style>
