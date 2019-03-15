<template>
  <div class="card mb-4 shadow">
    <div class="card-body">
      <div class="media">
        <img class="avatar-large" :src="user.avatar" alt="">
        <div class="media-body">
          <h2 class="media-heading">{{user.name}} ({{ userPostsCount }} posts)</h2>
        </div>
      </div>
      {{post.text}}
      <p class="text-secondary">
        <AppDate
          :timestamp="post.publishedAt"
        />
      </p>
    </div>
  </div>
</template>
<script>
import sourceData from '@/data'
import AppDate from './AppDate'
export default {
  props: {
    post: {
      required: true,
      type: Object
    }
  },
  components: {
    AppDate
  },
  computed: {
    user () {
      return sourceData.users[this.post.userId]
    },
    userPostsCount () {
      return Object.keys(this.user.posts).length
    }
  }
}
</script>
<style scoped>
  .avatar-large {
    width: 36px;
    height: 36px;
    border-radius: 50%;
  }
</style>
