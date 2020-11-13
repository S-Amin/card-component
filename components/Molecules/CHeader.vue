<template>
  <header class="header-root" v-if="title || subtitle || avatarUrl || loading">
    <CImg
      v-if="avatarUrl || loading"
      :src="avatarUrl"
      class="avatar-img"
      width="60"
      height="60"
      :avatar="true"
      :loading="true"
    />
    <div class="header-text">
      <Title>
        {{ title }}
      </Title>
      <SecTxt>
        {{ subtitle }}
      </SecTxt>
    </div>
  </header>
</template>

<script>
import Title from "../Atoms/Title";
import SecTxt from "../Atoms/SecTxt";
import CImg from "../Molecules/CImg";

export default {
  components: { Title, SecTxt },
  props: {
    title: {
      type: String,
      require: true
    },
    subtitle: String,
    avatarUrl: String,
    loading: Boolean
  }
};
</script>

<style lang="scss" scoped>
@import "@/assets/sass/main.var";

.header-root {
  display: flex;
  flex-direction: row;
  .avatar-img {
    margin-right: $spacing;
  }
}
.header-text {
  display: flex;
  flex-direction: column;
  justify-content: center;
  text-align: left;
}
</style>
