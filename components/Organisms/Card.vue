<template>
  <article
    :class="{ loading, card: true, clickable: linkTo || onClick }"
    @click="open"
  >
    <CImg
      v-if="coverImgUrl || loading"
      class="cover-img"
      :height="coverImgHeight"
      :src="coverImgUrl"
      :cover="true"
      :loading="loading"
    />
    <CHeader
      :class="{ 'card-header': true, 'on-top': headerOnTop }"
      :title="loading ? '' : title"
      :subtitle="loading ? '' : subtitle"
      :avatarUrl="avatarUrl"
      :loading="loading"
    />
    <CBody class="card-body" :loading="loading">
      <slot />
    </CBody>
    <CFooter class="card-footer" v-if="$slots.footer && !loading">
      <slot name="footer" />
    </CFooter>
  </article>
</template>

<script>
import CHeader from "../Molecules/CHeader";
import CBody from "../Molecules/CBody";
import CImg from "../Molecules/CImg";
import CFooter from "../Molecules/CFooter";

export default {
  components: { CHeader, CBody, CFooter, CImg },
  props: {
    title: {
      type: String,
      require: true
    },
    subtitle: String,
    coverImgUrl: String,
    coverImgHeight: String,
    avatarUrl: String,
    linkTo: String,
    onClick: Function,
    headerOnTop: Boolean,
    loading: {
      type: Boolean,
      default: false
    }
  },
  methods: {
    open() {
      if (this.linkTo && this.onClick === undefined) {
        window.open(this.linkTo, "_blank");
      } else if (this.onClick) {
        this.onClick();
      }
    }
  }
};
</script>

<style lang="scss" scoped>
@import "@/assets/sass/main.var";

.card {
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  min-width: 250px;
  height: 100%;
  border: 1px solid #ced4da;
  border-radius: 5px;
  padding: $spacing;
  padding-top: 0;
  overflow: hidden;

  &.clickable {
    cursor: pointer;
  }

  &:hover {
    background-color: #f8f9fa;
  }
  &:focus {
    outline: none;
    box-shadow: 0 0 3pt 2pt #dee2ff;
  }
}

.cover-img {
  margin-right: -$spacing;
  margin-left: -$spacing;
}

.card-header {
  margin-top: $spacing;
}

.card-body {
  margin-top: $spacing;
  margin-bottom: $spacing;
  justify-self: stretch;
}

.card-footer {
  margin: -$spacing;
  margin-top: auto;
  padding: $spacing;
  border-top: 1px solid #ced4da;
}

.on-top {
  order: -1;
  margin-bottom: $spacing;
}
</style>
