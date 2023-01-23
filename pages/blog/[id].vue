<template>
  <div>
    <div>
      <img :src="data.image" />
    </div>
    <div>
      <h1>{{ data.title }}</h1>
      <p>{{ data.date }}</p>
      <ContentDoc />
    </div>
  </div>
</template>

<script setup>
// const { data } = await useAsyncData("blogQuery", () =>
//   queryContent("/blog").sort({ id: -1 }).find()
// );
// ↑は記事全部を取得する処理で、ここでは記事1件の取得で良いので下記のようにする
// URLのパスを取得する
const path = useRoute().path;
console.log(path);
// URLのパスを元に記事を取得してdataに格納する
const { data } = await useAsyncData(path, () => queryContent(path).findOne());
</script>