<template>
  <div class="posts">
    <div v-if="posts.length > 0">
      <h2>Posts</h2>
      <div class="posts__wrapper">
        <post-item-vue
          v-for="post in posts"
          :post="post"
          :key="post.id"
          @remove="this.$emit('remove', post)"
        />
      </div>
    </div>

    <h2 style="color: red" v-else>Post list is empty</h2>
  </div>
</template>

<script>
import PostItemVue from "./PostItem.vue";
export default {
  components: {
    PostItemVue,
  },
  props: {
    posts: {
      type: Array,
      required: true,
    },
  },
};
</script>

<style scoped>
.posts {
  margin: 60px 0;
  padding: 20px 0;
  position: relative;
}

.posts__wrapper {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  align-items: center;
}

h2 {
  color: #008080;
  text-align: center;
  margin: 10px;
}
</style>
