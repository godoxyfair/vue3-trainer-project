<template>
  <div class="stickers">
    <!--Динамичесое изменение cо слушателем события v-on:click называется реактивность-->
    <div class="post">
      <div>
        <div><strong>Name:</strong> {{ post.title }}</div>
        <div><strong>Description:</strong> {{ post.body }}</div>
      </div>
      <div class="post__btns">
        <my-button @click="$emit('remove', post)">Delete</my-button>
      </div>
    </div>
  </div>
</template>

<script>
import MyButton from '@/components/UI/MyButton'
export default {
  components: { MyButton },
  props: {
    post: {
      type: Object,
      required: true
    }
  }
}
</script>

<style scoped>
.stickers {
  display: flex;
  flex-wrap: wrap;
}
.post {
  padding: 15px;
  margin: 20px 0 0 10px; /* top left bottom right */
  flex: 0 1 200px; /*эта *штука формирует динамическую ширину*/
  border: 2px solid cornflowerblue;
  flex-shrink: 1;
  flex-grow: 1;
}
.post:hover {
  box-shadow: 0 0 15px cornflowerblue;
}
.post__btns {
  display: flex;
  margin-top: 10px;
  justify-content: flex-end;
}
</style>
