<template>
  <nuxt-link :to="'/users/' + id">
    <article class="user">
      <div class="thumbnail" :style="{backgroundImage: 'url(' + thumbnail + ')'}"></div>
      <h1>{{ name }}</h1>
      <p>{{ email }}</p>
      </article>
  </nuxt-link>

</template>

<script>
export default {
  props: ["thumbnail", "name", "email", "id"]
};
</script>

<style scoped>
a {
  text-decoration: none;
  color: black;
}
.user {
  box-sizing: border-box;
  width: 280px;
  padding: 8px;
  border: 1px solid #ccc;
  box-shadow: 0 2px 2px #aaa;
  margin: 10px;
}
.thumbnail {
  background-position: center;
  background-size: cover;
  width: 100%;
  height: 200px;
}
</style>
