<template>
  <div>
    <form class="form" @submit.prevent>
      <h1>New Sticker</h1>
      <!--Директива v-bind для получения значения из компонент input-->
      <!--Директива v-model для двустроннего связывания-->
      <textarea
        class="input"
        placeholder="Name"
        v-model="post.title"
      />
      <textarea
        class="input"
        placeholder="Description"
        v-bind:value="post.body"
        @input="post.body = $event.target.value"
      />
      <my-button class="btm" @click="createPost" style="align-self: flex-end; margin-top: 10px">Create</my-button>
    </form>
  </div>
</template>

<script>
import MyButton from '@/components/UI/MyButton'
export default {
  components: { MyButton },
  // передаем значения из input наверх в App
  data () {
    return {
      post: {
        title: '',
        body: ''
      }
    }
  },
  methods: {
    createPost () {
      this.post.id = Date.now()
      this.$emit('create', this.post)
      this.post = {
        title: '',
        body: ''
      }
    }
  }
}
</script>

<style>
.form {
  display: flex;
  flex-direction: column;
}
.input {
  padding: 5px;
  margin-top: 5px;
  flex: 0 1 100px;
  border: 2px solid cornflowerblue;
}
.input:hover {
  box-shadow: 0 0 10px cornflowerblue;
}
</style>
