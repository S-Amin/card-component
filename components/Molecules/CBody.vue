<template>
  <section>
    <div class="card-body-skeleton" v-if="loading">
      <p />
      <p />
      <p />
    </div>
    <slot v-else />
  </section>
</template>

<script>
export default {
  props: {
    loading: Boolean
  }
};
</script>

<style lang="scss" scoped>
.loading {
  .card-body-skeleton p {
    height: 1.3em;
    margin-bottom: 5px;

    &:nth-child(1) {
      width: 60%;
    }
    &:nth-child(2) {
      width: 85%;
    }
    &:nth-child(3) {
      width: 70%;
    }
  }
}
</style>
