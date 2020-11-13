<template>
  <footer>
    <SecTxt v-if="isTxt">
      {{ $slots.default[0].text }}
    </SecTxt>
    <slot v-else />
  </footer>
</template>

<script>
import SecTxt from "../Atoms/SecTxt";

export default {
  components: { SecTxt },
  data() {
    return {
      isTxt:
        this.$slots.default?.length === 1 &&
        this.$slots.default[0].tag === undefined
    };
  }
};
</script>

<style lang="scss" scoped></style>
