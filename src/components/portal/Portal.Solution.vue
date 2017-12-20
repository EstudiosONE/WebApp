<template>
  <div class="content" id="portal-solution">
    <div class="title" >
      <div id="title-bkg">
        <div id="title">
          <h1><span style="font-weight: 100;">iGS</span> <span>Suite</span></h1>
          <h3>AIO Management solution</h3>
        </div>
      </div>
    </div>
    <div id="content">
      
    </div>
  </div>
</template>

<script>
export default {
  name: "PortalStart"
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
@import url("https://fonts.googleapis.com/css?family=Titillium+Web");
.content {
  position: relative;
  display: flex;
  justify-content: center;
  align-content: center;
  flex-flow: column wrap;
  height: auto;
  width: 100%;
}
.title {
  display: flex;
  flex-flow: row wrap;
  align-content: center;
  justify-content: center;
  background-image: url("../../assets/portal/solution-bkg.jpg");
  background-size: cover;
  height: 600px;
  width: 100%;
}
#title {
  display: flex;
  flex-flow: column wrap;
  justify-content: center;
  align-content: center;
}
#title-bkg {
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
  display: flex;
  flex-flow: row wrap;
  align-content: center;
  justify-content: center;

  width: inherit;
  height: 100%;
}
#content {
  display: flex;
  flex-flow: row wrap;
  justify-content: center;
  width: 100%;
  background-image: url("../../assets/portal/start-content-bkg2.jpg");
  background-size: cover;
}
#content p {
  width: 800px;
  margin-left: 50px;
  margin-right: 50px;
  margin-top: 0px;
  text-align: justify;
  font-family: "Titillium Web", sans-serif;
  font-weight: 100;
  font-size: 24px;
  color: #252525;
}
#content h2 {
  width: 800px;
  margin-left: 50px;
  margin-right: 50px;
  margin-bottom: 0px;
  text-align: justify;
  font-family: "Titillium Web", sans-serif;
  font-size: 36px;
  color: #252525;
}
h1 {
  margin: 0;
  font-family: "Titillium Web", sans-serif;
  font-size: 72px;
  color: white;
  text-shadow: 0 0 4px #000;
  -webkit-font-smoothing: antialiased;
  font-weight: bold;
}
h3 {
  margin: 0;
  font-family: "Titillium Web", sans-serif;
  font-size: 24px;
  color: white;
  text-shadow: 0 0 4px #000;
  -webkit-font-smoothing: antialiased;
  font-weight: lighter;
}
</style>
