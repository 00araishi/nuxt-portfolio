<template>
  <div>
    <div v-for="singleData in data" :key="singleData.id">
      {{ singleData.title }}<br />
      {{ singleData.date }}<br />
      <hr />
      <img :src="singleData.image" />
    </div>
  </div>
</template>

<script setup>
const { data } = await useAsyncData("blogQuery", () =>
  queryContent("/blog").sort({ id: -1 }).find() // 変更
);
</script>