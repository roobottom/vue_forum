<template>
  <div>
    <h1>Welcome to the forum</h1>
    <ThreadList :threads="threads" />
  </div>
</template>

<script>
import sourceData from '@/data'
import ThreadList from '@/components/ThreadList'
console.log(sourceData)
export default {
  components: {
    ThreadList
  },
  data () {
    return {
      threads: Object.values(sourceData.threads),
      posts: sourceData.posts,
      users: sourceData.users
    }
  }
}
</script>