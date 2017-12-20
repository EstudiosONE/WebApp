<template>
  <div id="suite" class="content">
    <suite-login/>
  </div>
</template>

<script>
import SuiteLogin from './Login/Login'

export default {
  name: 'Suite',
  components: {
    SuiteLogin
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.content{
  height: 100%;
  width: 100%;
}
</style>
