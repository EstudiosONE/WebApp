<template>
  <div class="content" id="portal-header">
    <div id="img">
      <img src="../../assets/LogoCorp.png">
    </div>
    <div id="menu">
      <button type="button" @click="goTo('#')" href="">Inicio</button>
      <button type="button" @click="goTo('#portal-solution')" href="">Solución</button>
      <button type="button" @click="goTo('#portal-contact')" href="">Contacto</button>
    </div>
    <div id="login">
      <button type="button" @click="goToLogin()" href="">Login</button>
    </div>
  </div>
</template>

<script>
import { EventBus } from '../../event-bus';

export default {
  name: "PortalHeader",
  data() {
    return {
      clickCount: 0
    }
  },
  methods:{
    goTo: function(ref){
      location.href=ref;
    },
    goToLogin: function(){
      EventBus.$emit('goToAppLogin');
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
@import url("https://fonts.googleapis.com/css?family=Titillium+Web");
.content {
  z-index: 10000;
  position: fixed;
  display: flex;
  align-content: center;
  justify-content: space-between;
  background-color: white;
  box-shadow: 0 0 6px #000;
  grid-template-columns: 216px 12px 1fr 12px 216px;
  grid-template-rows: 1fr;
  height: 72px;
  width: 100%;
}
#img, #menu, #login{
  width: 1000px;
  display: flex;
  flex-wrap: wrap;
}
#img{
  justify-content: flex-start;
}
#menu{
  justify-content: center;
}
#login{
  justify-content: flex-end;
}
button {
  display: flex;
  justify-content: center;
  align-content: center;
  padding: 24px;
  min-width: 100px;
  text-decoration: none;
  font-family: "Titillium Web";
  font-size: 16px;
  color: #252525;
  background-color: #FFFFFF;
  border: none;
}
button:hover {
  background-color: #252525;
  color: #ffffff;
}
button:focus{
  border: none;
  outline: none;
}
img {
  height: 72px;
}
</style>
