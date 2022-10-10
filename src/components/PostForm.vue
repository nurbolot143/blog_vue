<template>
  <div class="form">
    <form @submit.prevent="createPost">
      <h3>Create Post</h3>
      <my-input v-model="post.title" placeholder="Title" />
      <my-input v-model="post.body" placeholder="Description" />
      <my-button>Submit</my-button>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      post: {
        title: "",
        body: "",
      },
    };
  },
  methods: {
    createPost() {


      this.id = Date.now();
      this.$emit("create", this.post);
      this.post = {
        title: "",
        body: "",
      };
    },
  },
};
</script>

<style scoped>
.form {
  width: 400px;
  padding: 30px;
  border-radius: 10px;
  border: 1px solid gray;
  margin: 0 auto;
}

form {
  display: flex;
  flex-direction: column;
}

form input,
button {
  padding: 10px 25px;
  border-radius: 5px;
  margin: 20px 0;
  border: 1px solid #008080;
}

form button {
  background: #008080;
  color: #faebd7;
  text-transform: uppercase;
  align-self: end;
  cursor: pointer;
}
</style>
