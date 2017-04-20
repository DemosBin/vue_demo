<template>
  <div v-html='content'></div>
</template>
<script>
export default {
  data () {
    return {
      content: ''
    }
  },
  created () {
    this.get_data(this.$route.params.id)
  },
  methods: {
    get_data: function (id) {
      var v = this
      v.$api.get('topic/' + id, null, function (r) {
        console.log(r.data.content)
        v.content = r.data.content
      })
    }
  }
}
</script>
