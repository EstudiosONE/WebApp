<template>
  <div id="app">
    <portal/>
  </div>
</template>

<script>
import Portal from "./components/portal/Portal";
import Suite from "./components/app/Suite";
import Vue from 'vue';
import { EventBus } from "./event-bus"

export default {
  name: "app",
  components: {
    Portal,
    Suite
  },
  created() {
    EventBus.$on('goToAppLogin', goToAppLogin =>{
      document.getElementById('portal').remove();
      new Vue({
        el: '#app',
        template: '<suite/>',
        components: { Suite }
      })
    });
  },
  beforeDestroy(){
    EventBus.$off('goToAppLogin')
  },
};
</script>

<style>

</style>
