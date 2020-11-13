<template>
  <p class="sub-title"><slot /></p>
</template>

<style lang="scss" scoped>
@import "@/assets/sass/main.var";
.sub-title {
  color: $secondary-color;
  font-size: 0.9em;
  font-weight: 500;
}

.loading {
  .sub-title {
    height: 0.8em;
    width: 9em;
  }
}
</style>
