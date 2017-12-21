<template>
  <div id="suite-main" class="content">
    <button id="openMenu" type="button" @click="OpenMenu">
      <svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 24 24" version="1.1">
        <g id="surface1">
          <path d="M 2 5 L 2 7 L 22 7 L 22 5 Z M 2 11 L 2 13 L 22 13 L 22 11 Z M 2 17 L 2 19 L 22 19 L 22 17 Z "></path>
        </g>
      </svg>
    </button>
    <div id="header">
      <div>
        <h1><span style="font-weight: 100;">iGS</span> <span>Suite</span></h1> 
      </div>
    </div>
    <div id="menu" :style="menuStyle">
      <img src="../../../assets/LogoCorp.png">
    </div>
    
  </div>
</template>

<script>
import JSSHA from "jssha";
export default {
  name: "Suite-Main",
  components: {},
  data() {
    return{
      menuStyle: {
        'grid-column-end': '3',
        'background-color': 'transparent'
      },
      isMenuActive: false,
    }
  },
  methods: {
    OpenMenu(){
      if(this.isMenuActive){
        this.menuStyle = {
          'width': '72px',
          'background-color': 'transparent',
          'box-shadow': 'none'
        }
        this.isMenuActive = false;
      }
      else{
        this.menuStyle={
          'width': '264px',
          'background-color': '#FFFFFF',
          'box-shadow': '0 0 8px #000'
        }
        this.isMenuActive = true;
      }
    }
  },
  mounted(){
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
@import url("https://fonts.googleapis.com/css?family=Titillium+Web");
.content {
  position: absolute;
  background-color: #0078d7;
  height: 100%;
  width: 100%;
  display: grid;
  grid-template-columns: 12px 60px 12px 180px 1fr;
  grid-template-rows: 72px 12px 1fr;
}
#openMenu{
  position: absolute;
  width: 100%;
  height: 100%;
  grid-row-start: 1;
  grid-row-end: 2;
  grid-column-start: 1;
  grid-column-end: 3;
  padding: 24px;
  background-color: #FFFFFF;
  border: 0px solid transparent;
  color: #151515;
  z-index: 220;
}
#openMenu svg g path{
  fill: #151515;
}
#openMenu:focus{
  outline: none;
}
#openMenu:hover svg g path{
  fill: #0078d7;
}
#menu{
  position: absolute;
  width: 72px;
  height: 100%;
  grid-column-start: 1;
  grid-row-start: 1;
  grid-row-end: 4;
  background-color: #FFFFFF;
  z-index: 200;
  transition: .2s;
  overflow: hidden;
}
#menu img{
  height: 72px;
  float: right;
  padding: 0 0 0 0;
}
#header{
  position: absolute;
  height: 100%;
  width: 100%;
  grid-row-start: 1;
  grid-row-end: 2;
  grid-column-start: 1;
  grid-column-end: 6;

  display: grid;
  grid-template-columns: 84px 1fr;

  background-color: #FFFFFF;
  box-shadow: 0 0 8px #000;
  z-index: 100;
}
#header div{
  position: absolute;
  height: 100%;
  grid-column: 2;
  grid-row-start: 1;
  grid-row-end: 3;
  display: flex;
  flex-flow: column wrap;
  justify-content: center;
  align-content: center;
}
#header div h1{
  font-family: 'Titillium Web';
  font-size: 24px;
  color: #151515;
  margin: 0px;
}

</style>
