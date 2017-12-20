<template>
  <div id="suite" class="content">
    <suite-login/>
  </div>
</template>

<script>
import SuiteLogin from './Login/Login'
import SuiteMain from './Main/Main'
import { EventBus } from '../../event-bus';

export default {
  name: 'Suite',
  components: {
    SuiteLogin,
    SuiteMain
  },
  created() {
    EventBus.$on('Suite-Login-Successful', goToAppLogin =>{
      document.getElementById('suite-login').remove();
      new Vue({
        el: '#suite',
        template: '<suite-main/>',
        components: { SuiteMain }
      })
    });
  },
  beforeDestroy(){
    EventBus.$off('Suite-Login-Successful')
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.content{
  position: absolute;
  height: 100%;
  width: 100%;
}
</style>
