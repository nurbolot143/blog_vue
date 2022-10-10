<template>
  <div class="post">
    <div>
      <div class="title"><strong>Title</strong> {{ post.title }}</div>
      <div class="descr">
        <strong>Description</strong>
        <p>{{ post.body }}</p>
      </div>
    </div>
    <div class="btn">
      <my-button @click="this.$emit('remove', post)">Delete</my-button>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    post: {
      type: Object,
      required: true,
    },
  },
};
</script>

<style scoped>
.post::after {
  position: absolute;
  content: "";
  top: 0;
  left: 50%;
  transform: translateX(-50%);
  width: 70%;
  height: 1px;
  background: #008080;
}

.post {
  margin: 20px;
  padding: 20px;
  border-radius: 3px;
  width: 300px;
  border: 1px solid gray;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.title {
  font-size: 25px;
}

.descr {
  font-size: 20px;
  margin-top: 15px;
}

.post > div:first-child {
  margin-bottom: 20px;
}

.btn {
  text-align: right;
}
</style>
