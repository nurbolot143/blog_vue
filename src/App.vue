<template>
	<div class="app">
		<h1>Posts Page</h1>
		<div class="showBtn">
			<my-button @click="showDialog">Create post</my-button>
		</div>
		<my-dialog v-model:show="dialogVisible">
			<post-form @create="createPost" />
		</my-dialog>

		<post-list :posts="posts" @remove="removePost" />
	</div>
</template>

<script lang="js">
import PostForm from '@/components/PostForm.vue'
import PostList from '@/components/PostsList.vue'

export default {
  components: {
    PostForm,
    PostList,
  },

  data() {
    return {
      posts: [
        { id: 1, title: "JavaScript", body: "About JavaScript" },
        { id: 2, title: "JavaScrip2 ", body: "About JavaScrip2 " },
        { id: 3, title: "JavaScrip 3", body: "About JavaScrip 3" },
      ],
      dialogVisible: false,
    };
  },

  methods: {
    createPost(post) {
      this.posts.push(post);
      this.dialogVisible = false;
    },
    removePost(post) {
      this.posts = this.posts.filter((item) => item.id !== post.id);
    },
    showDialog() {
      this.dialogVisible = true;
    },
    async fetchUsers () {
      try {
        const response = await axios.get(`https://jsonplaceholder.typicode.com/posts?_limit=10`).then(res => res).then(res => res ).then(res => res).catch(err=>err)
      } catch (err) {
        alert("Error")

      }
    }
  },
};
</script>

<style>
* {
	font-family: "Lucida Sans", "Lucida Sans Regular", "Lucida Grande",
		"Lucida Sans Unicode", Geneva, Verdana, sans-serif;
	margin: 0;
	padding: 0;
	box-sizing: border-box;
}

.app {
	max-width: 1140px;
	padding: 15px;
	margin: 0 auto;
}

.showBtn {
	text-align: right;
}
</style>
