<template>
  <div class="app">
    <my-dialog :show="true">
      <post-form @create="createPost" />
    </my-dialog>
    <post-list :posts="posts" @remove="removePost" />
  </div>
</template>
<script>
import PostList from '@/components/PostList.vue';
import PostForm from '@/components/PostForm.vue';
export default {
  components: {
    PostList,
    PostForm,
  },
  data() {
    return {
      posts: [
        { id: 1, title: 'JS1', body: '123' },
        { id: 2, title: 'JS2', body: '1234' },
        { id: 3, title: 'JS3', body: '1235' },
      ],
    };
  },
  methods: {
    createPost(post) {
      this.posts.push(post);
    },
    removePost(post) {
      this.posts = this.posts.filter((p) => p.id !== post.id);
    },
  },
};
</script>
<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
.app {
  padding: 20px;
}
</style>
