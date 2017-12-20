<template>
  <div id="suite-login" class="content">
    <div style="display: flex; flex-flow: column wrap; justify-content: center;">
      <h1><span style="font-weight: lighter;">iGS</span> <span>Suite</span></h1>
      <div id="loginLayout">
        <img style="margin-left: 12px; margin-top: 12px;" src="../../../assets/LogoCorp.png">
        <h3>Iniciar sesión en iGS Suite:</h3>
        <form>
          <label for="user">Usuario:</label>
          <input id="user" type="user">
          <label for="pass">Contraseña</label>
          <input id="pass" type="password">
          <div style="display: flex; flex-flow: row wrap; justify-content: flex-end;">
            <input id="submit" type="submit" value="Login" @click.prevent="Login">
          </div>
        </form>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Suite-Login',
  components: {
  },
  methods:{
    Login(){
      console.warn('Login');
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.content{
  position: absolute;
  background-color: #0078d7;
  height: 100%;
  width: 100%;

  display: flex;
  flex-flow: row wrap;
  justify-content: center;
  
}
#loginLayout{
  background-color: white;
  width: 480px;
  height: 400px;
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
form{
  padding: 36px;
  display: flex;
  flex-flow: column wrap;
  justify-content: flex-end;
}
#user, #pass, #submit{
  font-family: "Titillium Web", sans-serif;
  font-size: 16px;
  height: 24px;
  margin-bottom: 12px;
  margin-top: 4px;
}
#user, #pass{
  border: none;
  border-bottom-color: #0078d7;
  border-bottom-style: solid;
  border-bottom-width: 1px;
}
input:focus{
  outline: none;
}
#submit{
  float: right;
  height: 48px;
  width: 120px;
  margin-bottom: 12px;
  margin-top: 12px;
  background-color: white;
  color: #0078d7;
  border: 1px solid #0078d7; 
}
#submit:hover{
  background-color: #0078d7;
  color: white;
}
label{
  font-family: "Titillium Web", sans-serif;
}
</style>
