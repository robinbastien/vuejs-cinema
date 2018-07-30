<template>
  <div>
    <div class="session-time">
      {{ formatSessionTime(session.time) }}
    </div>
  </div>
</template>
<script>
export default {
  props: ['session'],
  methods: {
    formatSessionTime(raw) {
      return this.$moment(raw).format('h:mm A');
    }
  }
}
</script>
