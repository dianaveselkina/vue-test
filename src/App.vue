<template>
  <div class="app">
    <post-form />
    <post-list :posts="posts" />
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
      title: '',
      body: '',
    };
  },
  methods: {
    createPost() {
      const newPost = {
        id: Date.now(),
        title: this.title,
        body: this.body,
      };
      this.posts.push(newPost);
      (this.title = ''), (this.body = '');
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
