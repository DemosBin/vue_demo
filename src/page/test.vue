<template>
  <div style="margin-left:10%">
    <div id="app" style="width:40%;float:left;height:900px;transform: perspective(600px) rotateY(4deg);    margin-top: 20px;">
      {{code}}
    </div>
    <div id="textarea" style="width:40%;float:left;background: #000;opacity: 0.6;color: red;height:900px;transform: perspective(600px) rotateY(-4deg);    margin-top: 20px;">
      {{code}}
    </div>
    <div v-html="styleCode">
      
    </div>
  </div>
</template>
<script>
export default {
  name: 'app',
  components: {
  },
  data () {
    return {
      code: ``,
      finalCode: `
      #app{
        background: gray;
      }`
    }
  },
  created () {
    var n = 0
    setInterval(() => {
      this.code = this.finalCode.substring(0, n)
      n += 1
    }, 100)
  },
  computed: {
    styleCode () {
      return '<style>' + this.code + '</style>'
    }
  }
}
</script>
