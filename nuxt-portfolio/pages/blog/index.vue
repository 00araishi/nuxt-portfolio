<template>
  <div>
    <div v-for="singleData in data" :key="singleData.id">
      {{ singleData.title }}<br />
      {{ singleData.date }}<br />
      <NuxtLink :to="singleData._path">続きを読む</NuxtLink><br />
      <img :src="singleData.image" />
      <hr />
    </div>
  </div>
</template>

<script setup>
const { data } = await useAsyncData("blogQuery", () =>
  queryContent("/blog").sort({ id: -1 }).find()
);
</script>