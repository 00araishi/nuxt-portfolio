<template>
  <div>
    <div v-for="singleData in data" :key="singleData.id">
      {{ singleData.title }}<br />
      {{ singleData.date }}<br />
      {{ singleData }}<br />
      <hr />
    </div>
  </div>
</template>

<script setup>
const { data } = await useAsyncData("blogQuery", () =>
  queryContent("/blog").find()
);
</script>