<template>
  <div class="container">
    <div class="item">
      <Card
        title="Card title"
        subtitle="Card subtitle"
        coverImgUrl="https://picsum.photos/id/2/5616/3744"
        linkTo="https://www.notion.so/Card-component-206dfb9d6ba34e56b98853f4e0387701"
        :loading="loading"
        >Lorem ipsum dolor sit amet consectetur adipisicing elit. Harum, beatae.
        Saepe optio voluptas deserunt iure accusantium autem dicta cumque
        aliquam.
        <template #footer>
          Card footer
        </template>
      </Card>
    </div>
    <div class="item">
      <Card
        title="No Click Card"
        avatarUrl="https://picsum.photos/id/203/4032/3024"
        :loading="loading"
        >Lorem ipsum dolor sit amet consectetur adipisicing elit. Harum, beatae.
        Saepe optio voluptas deserunt iure accusantium autem dicta cumque
        aliquam.
      </Card>
    </div>
    <div class="item">
      <Card
        :onClick="clickHandle('no cover image, no avatar card')"
        :loading="loading"
        >Lorem ipsum dolor sit amet consectetur adipisicing elit. Laborum,
        eligendi, quam quo voluptas asperiores excepturi praesentium earum quasi
        veritatis, libero minus et possimus debitis laudantium suscipit culpa
        quas reiciendis. Voluptatem illum nisi temporibus animi corrupti ex
        tempora nesciunt eveniet, facere maiores nostrum recusandae, accusamus
        iure numquam amet, totam explicabo obcaecati!
        <template #footer>
          Card footer
        </template>
      </Card>
    </div>
    <div class="item">
      <Card
        title="Card title"
        subtitle="Card subtitle"
        coverImgUrl="https://picsum.photos/id/2/5616/3744"
        avatarUrl="https://picsum.photos/id/203/4032/3024"
        :onClick="clickHandle('custom click func')"
        :loading="loading"
        >Lorem ipsum dolor sit amet consectetur adipisicing elit. Harum, beatae.
        Saepe optio voluptas deserunt iure accusantium autem dicta cumque
        aliquam.
        <template #footer>
          Card footer
        </template>
      </Card>
    </div>
    <div class="item" style="max-width: 500px;">
      <Card
        title="Card title"
        subtitle="Card subtitle"
        coverImgUrl="https://picsum.photos/id/2/5616/3744"
        avatarUrl="https://picsum.photos/id/203/4032/3024"
        coverImgHeight="200"
        :onClick="clickHandle('cover image with fixed height')"
        :loading="loading"
        >Lorem ipsum dolor sit amet consectetur adipisicing elit. Harum, beatae.
        Saepe optio voluptas deserunt iure accusantium autem dicta cumque
        aliquam.
        <template #footer>
          Card footer
        </template>
      </Card>
    </div>
    <div class="item" style="max-width: 500px;">
      <Card
        title="Card title"
        subtitle="Card subtitle"
        coverImgUrl="https://picsum.photos/id/216/2500/1667"
        avatarUrl="https://picsum.photos/id/203/4032/3024"
        :onClick="clickHandle('cover image keep ratio')"
        :loading="loading"
        >Lorem ipsum dolor sit amet consectetur adipisicing elit. Harum, beatae.
        Saepe optio voluptas deserunt iure accusantium autem dicta cumque
        aliquam.
        <template #footer>
          Card footer
        </template>
      </Card>
    </div>
    <div class="item">
      <Card
        title="Card title"
        subtitle="Card subtitle"
        coverImgUrl="https://picsum.photos/id/2/5616/3744"
        avatarUrl="https://picsum.photos/id/203/4032/3024"
        :onClick="clickHandle('custom click func')"
        headerOnTop=""
        :loading="loading"
        >Lorem ipsum dolor sit amet consectetur adipisicing elit. Harum, beatae.
        Saepe optio voluptas deserunt iure accusantium autem dicta cumque
        aliquam.
        <template #footer>
          Card footer
        </template>
      </Card>
    </div>
    <div class="item">
      <Card
        title="Card title"
        subtitle="Card subtitle"
        coverImgUrl="https://picsum.photos/id/2/5616/3744"
        avatarUrl="https://picsum.photos/id/203/4032/3024"
        :onClick="clickHandle('custom click func')"
        :loading="loading"
      >
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Dolores porro
        ad labore voluptates sapiente praesentium.
        <template #footer>
          Card footer
        </template>
      </Card>
    </div>
    <div class="item">
      <Card
        title="Card title"
        subtitle="Card subtitle"
        coverImgUrl="https://aaa.bbb"
        avatarUrl="https://picsum.photos/idd/203/4032/3024"
        :onClick="clickHandle('custom click func')"
        :loading="loading"
        >Lorem ipsum dolor sit amet consectetur adipisicing elit. Nisi eius,
        tempora magni consequatur molestiae repellendus. Cum consectetur laborum
        veritatis eveniet asperiores repellat quo architecto porro officiis?
        Iure vel corporis quisquam eveniet sed tempora aperiam magni eaque,
        asperiores, reprehenderit corrupti eius?
        <template #footer>
          Card footer
        </template>
      </Card>
    </div>
    <div class="item">
      <Card
        title="Card title"
        subtitle="Card subtitle"
        coverImgUrl="https://picsum.photos/id/2/5616/3744"
        avatarUrl="https://picsum.photos/id/203/4032/3024"
        :loading="loading"
        >Lorem ipsum dolor sit amet consectetur adipisicing elit. Harum, beatae.
        Saepe optio voluptas deserunt iure accusantium autem dicta cumque
        aliquam.
        <template #footer>
          Customize Footer
          <button>Share</button>
        </template>
      </Card>
    </div>
  </div>
</template>

<script>
import Card from "./Card";
export default {
  data() {
    return {
      loading: true
    };
  },
  methods: {
    clickHandle(msg) {
      return () => {
        alert(msg);
      };
    }
  },
  mounted() {
    setTimeout(() => {
      this.loading = false;
    }, 3000);
  }
};
</script>

<style lang="scss" scoped>
.container {
  padding: 20px;
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: space-between;
}
.item {
  margin: 20px;
  max-width: 300px;
}
</style>
