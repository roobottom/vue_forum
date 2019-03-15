<template>
  <form class="form mb-5" @submit.prevent="addPost">
      <textarea 
        class="form-control mb-2" 
        rows="10" 
        v-model="newPostText"
      ></textarea>
      <button class="btn btn-primary">Add post</button>
    </form>
</template>
<script>
export default {
  props: {
    threadId: {
      required: true
    }
  },
  data () {
    return {
      newPostText: ''
    }
  },
  methods: {
    addPost () {
      const postId = 'NewPost' + Math.random()
      const post = {
        text: this.newPostText,
        publishedAt: Math.floor(Date.now() / 1000),
        threadId: this.threadId,
        userId: 'FsCDAk9w8NeXEceLV87arpsXjnQ2',
        '.key': postId
      }
      this.newPostText = ''
      this.$emit('save', {post})
    }
  }
}
</script>
