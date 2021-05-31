<template>
  <nuxt-link :to="'/' + id">
    <div class="card container mt-3 mb-2">
      <div class="card-body">{{ pokemon }}</div>
    </div>
  </nuxt-link>
</template>

<script>
export default {
  name: "pokemon",
  props: ["pokemon", "id"],
};
</script>

<style lang="scss" scoped></style>
