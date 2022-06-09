<template>
  <div>
    {{ ip }}
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
  data() {
    return {
      ip: '',
    }
  },
  mounted() {
    this.getIp()
  },
  methods: {
    async getIp() {
      const ip = await this.$axios.$get('http://icanhazip.com')
      this.ip = ip
    },
  },
}
</script>
