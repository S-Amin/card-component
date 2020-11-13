<template>
  <figure :class="{ avatar, 'img-wrapper': true }" :style="style">
    <img
      v-if="!broken"
      class="image-responsive"
      :src="src"
      :alt="alt"
      @error="onErrorHandle"
    />
    <BrokenImg class="broken-img" v-else />
  </figure>
</template>

<script>
import BrokenImg from "../Atoms/BrokenImg";
export default {
  components: { BrokenImg },
  data() {
    return {
      broken: false
    };
  },
  props: {
    src: {
      type: String,
      require: true
    },
    alt: {
      type: String,
      require: true
    },
    width: String,
    height: String,
    cover: Boolean,
    avatar: Boolean,
    loading: Boolean
  },
  methods: {
    onErrorHandle() {
      this.broken = true;
      console.error("image url error");
    }
  },
  computed: {
    style() {
      const s = {};
      if (this.width) s["width"] = this.width + "px";
      if (this.height) s["height"] = this.height + "px";
      return s;
    }
  }
};
</script>

<style lang="scss" scoped>
@import "@/assets/sass/main.var";

.img-wrapper {
  overflow: hidden;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  background-color: #e9ecef;
}
.image-responsive {
  object-fit: cover;
  width: 100%;
  height: 100%;
}

.avatar {
  border-radius: 51%;
}

.loading {
  .img-wrapper {
    height: 200px;
    animation: pulse-bg 1s infinite;
  }
  .image-responsive {
    opacity: 0;
  }
  .broken-img {
    opacity: 0;
  }
}
</style>
