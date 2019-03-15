<template>
    <tr>
      <td>
        <router-link :to="{name: 'PageThreadShow', params: {id: thread['.key']}}">{{thread.title}}</router-link>
      </td>
      <td><a href="#">{{user.name}}</a></td>
      <td><AppDate :timestamp="thread.publishedAt"/></td>
      <td>{{repliesCount}} replies</td>
    </tr>
</template>

<script>
import sourceData from '@/data'
import AppDate from './AppDate'
export default {
  props: {
    thread: {
      required: true,
      type: Object
    }
  },
  components: {
    AppDate
  },
  computed: {
    repliesCount () {
      return Object.keys(this.thread.posts).length - 1
    },
    user () {
      return sourceData.users[this.thread.userId]
    }
  }
}
</script>
