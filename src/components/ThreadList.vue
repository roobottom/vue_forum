<template>
  <table class="table">
    <thead>
      <tr>
        <th>Subject</th>
        <th>User</th>
        <th>Published</th>
        <th>Replies</th>
      </tr>
    </thead>
    <tbody>
    <ThreadListItem
      v-for="thread in threads"
      :thread="thread"
      :key="thread['.key']"
    />
    </tbody>
  </table>
</template>

<script>
  import ThreadListItem from './ThreadListItem'
  export default {
    components: {
      ThreadListItem
    },
    props: {
      threads: {
        required: true,
        type: Array
      }
    }
  }
</script>