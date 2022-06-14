<template>
  <div v-show="posts.length > 0">
    <h3>Stickers</h3>
    <div class="list">
      <post-item
        v-for="post in posts"
        v-bind:post="post"
        v-bind:key="post.id"
        @remove="$emit('remove', post)"
      />
    </div>
  </div>
  <h2 v-show="posts.length === 0">List is empty</h2>
</template>

<script>
// чтобы добвить в список постов значения нужно использовать пропсы
// сам массив нельзя перенести в компонент так как компонент переиспользуемый
// и данные нужно подгружать из вне
import PostItem from '@/components/PostItem'
export default {
  components: { PostItem },
  props: {
    posts: {
      type: Array,
      required: true
    }
  }
}
</script>

<style>
.list {
  display: flex;
  flex-wrap: wrap;
}
</style>
