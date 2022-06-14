// likes and dislikes будут отображаься на странице
<template>
  <div class="app">
    <post-form @create="createPost"/>
    <!--Объявление пропсов для PostList короткая запись :posts="posts"-->
    <post-list v-bind:posts="posts" @remove="removePost"/>
  </div>
</template>

<script>
import PostList from '@/components/PostList'
import PostForm from '@/components/PostForm'
// создадим две модели
export default {
  components: {
    PostList, PostForm
  },
  data () {
    // создаем массив постов чтоб они подгружались в html компонент
    return {
      posts: [
        { id: 1, title: 'JS', body: 'Description' },
        { id: 2, title: 'Python', body: 'Description' },
        { id: 3, title: 'C++', body: 'Description' }
      ]
    }
  },
  // объявдение функции create post
  methods: {
    createPost (post) {
      this.posts.push(post)
    },
    removePost (post) {
      this.posts = this.posts.filter(p => p.id !== post.id)
    }
  }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
.app {
  padding: 10px;
}
</style>
