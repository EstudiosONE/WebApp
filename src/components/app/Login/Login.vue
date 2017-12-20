<template>
  <div id="suite-login" class="content">
    <div style="display: flex; flex-flow: column wrap; justify-content: center;">
      <h1><span style="font-weight: lighter;">iGS</span> <span>Suite</span></h1>
      <div id="loginLayout" class="loginStandBy" :class="{'loginError' : hasError}">
        <img style="margin-left: 12px; margin-top: 12px;" src="../../../assets/LogoCorp.png">
        <h3>Iniciar sesión en iGS Suite:</h3>
        <form>
          <label for="user">Usuario:</label>
          <input id="user" type="user" v-model="user" placeholder="Ej: 12345670" autocomplete="off">
          <label for="pass">Contraseña</label>
          <input id="pass" type="password" v-model="pass" autocomplete="off">
          <div style="display: flex; flex-flow: row wrap; justify-content: space-between;">
            <p class="loginStandBy"> {{messageError}} </p>
            <input id="submit" type="submit" value="Login" @click.prevent="Login">
          </div>
        </form>
      </div>
    </div>
  </div>
</template>

<script>
import JSSHA from "jssha";
import { EventBus } from '../../../event-bus';

export default {
  name: "Suite-Login",
  components: {},
  data() {
    return{
      user: "",
      pass: "",
      hasError: false,
      messageError: ''
    }
  },
  methods: {
    Login() {

      if(this.user=='' || this.pass==''){
        this.messageError='Debe ingresar usuario y contraseña, luego presionar "Enter" o "Login".'
        this.hasError= true;
      }
      else{
        if(this.user == '47378274' && this.pass == 'dierod17U21626'){
          EventBus.$emit('Suite-Login-Successful');
        }
        else{
          this.messageError="Usuario y/o contraseña incorrecta. Por favor verifique e inténtelo nuevamente."
          this.hasError= true;
        }
      var shaObj = new JSSHA("SHA-512","TEXT");
      shaObj.update(this.pass);

      var User = this.user;
      var Pass = shaObj.getHash("B64");   
      }
    },
  },
  mounted(){
    document.getElementById("user").focus();
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.content {
  position: absolute;
  background-color: #0078d7;
  height: 100%;
  width: 100%;
  display: flex;
  flex-flow: row wrap;
  justify-content: center;
}
#loginLayout {
  background-color: white;
  width: 480px;
  height: 400px;
  box-shadow: 0 0 4px #000;
  border-radius: 5px;
}
.loginStandBy{
  border-bottom: 8px solid #FFFFFF;
}
.loginStandBy p{
  margin-top: 12px;
  font-family: "Titillium Web", sans-serif;
  text-align: justify;
  color: #ffffff;
  width: 265px;
  height: 48px;
  overflow: hidden;
  text-overflow: ellipsis;
}
.loginError{
  border-bottom: 8px solid #e81123;
}
.loginError p{
  color: #e81123;
}

h1 {
  margin: 0;
  margin-bottom: 24px;
  font-family: "Titillium Web", sans-serif;
  font-size: 48px;
  text-align: center;
  color: white;
  text-shadow: 0 0 4px #000;
  -webkit-font-smoothing: antialiased;
  font-weight: bold;
}
h3 {
  margin: 0;
  margin-left: 36px;
  font-family: "Titillium Web", sans-serif;
  font-size: 20px;
  color: #151515;
  -webkit-font-smoothing: antialiased;
  font-weight: bold;
}
form {
  padding: 36px;
  display: flex;
  flex-flow: column wrap;
  justify-content: flex-end;
}
#user,
#pass,
#submit {
  font-family: "Titillium Web", sans-serif;
  font-size: 16px;
  height: 24px;
  margin-bottom: 12px;
  margin-top: 4px;
}
#user,
#pass {
  border: none;
  padding-left: 12px;
  padding-right: 12px;
  border-bottom-color: #0078d7;
  border-bottom-style: solid;
  border-bottom-width: 1px;
}
input:focus {
  outline: none;
}
#submit {
  float: right;
  height: 48px;
  width: 120px;
  margin-bottom: 12px;
  margin-top: 12px;
  background-color: white;
  color: #0078d7;
  border: 1px solid #0078d7;
}
#submit:hover {
  background-color: #0078d7;
  color: white;
}
label {
  font-family: "Titillium Web", sans-serif;
}

</style>
