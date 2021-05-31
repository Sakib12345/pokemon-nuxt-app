<template>
  <div>
    <div class="input-group input-group-lg container mt-lg-5 mt-5 mb-2 ml-2 ml-lg-5">
      <form class="form-inline " @submit.prevent="onSubmit">
        <div class="form-group mx-sm-3 mb-2">
          <input
            type="text"
            v-model="text"
            class="form-control"
            placeholder="Search here..."
          />
        </div>
        <button type="submit" class="btn btn-primary mb-2">Search</button>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  name: "SearchPokemons",
  data() {
    return {
      text: "",
    };
  },
  methods: {
      onSubmit(){
          this.$emit('search-text', this.text);
          this.text = '';
      }
  }
};
</script>

<style lang="scss" scoped></style>
