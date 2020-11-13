<template>
  <h2 class="title"><slot /></h2>
</template>

<style lang="scss" scoped>
@import "@/assets/sass/main.var";
.title {
  color: $primary-color;
  font-family: serif;
  font-weight: 700;
  margin-bottom: 5px;
}

.loading {
  .title {
    height: 1em;
    width: 8em;
  }
}
</style>
