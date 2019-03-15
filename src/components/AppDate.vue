<template>
  <time 
  datetime="" 
  :title="timestamp | humanDate">
  {{ timestamp | timeSince }}
  </time>
</template>
<script>
import moment from 'moment'
export default {
  props: {
    timestamp: {
      required: true,
      type: Number
    }
  },
  filters: {
    humanDate (date) {
      return moment.unix(date).format('MMMM Do YYYY, h:mm:ss a')
    },
    timeSince (date) {
      return moment.unix(date).fromNow()
    }
  }
}
</script>
