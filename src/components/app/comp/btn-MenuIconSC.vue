<template>
  <div id="btn-MenuIconSC" class="content" @click="click">
    <div id="icon">
        <svg viewBox="0 0 48 48" preserveAspectRatio="xMidYMid"  xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" version="1.1">
            <g id="surface1">
                <path :d='data'></path>
            </g>
        </svg>    
    </div>
    <div id="description">
        <p>
            {{description}}
        </p>
    </div>
  </div>
</template>

<script>
import { EventBus } from "../../../event-bus";
export default {
  name: "btn-MenuIconSC",
  props:[
      'description', 'data', 'event'
  ],
  methods: {
      click(){
        
      }
  },
  mounted(){
  }
};
</script>



<style scoped>
@import url("https://fonts.googleapis.com/css?family=Titillium+Web");

.content{
    position: relative;
    width: 144px;
    height: 144px;
    z-index: 101;
    background-color: white;
    margin: 16px;
    box-shadow: 0 0 4px #999999;
    display: grid;
    grid-template-columns: 1fr 36px 12px 48px 12px 36px 1fr;
    grid-template-rows: 1fr 36px 12px 48px 12px 36px 1fr;
    transition: .2s;
}
.content:hover{
    box-shadow: 0 0 12px #999999;
}

#icon{
    width: 100%;
    height: 100%;
    z-index: 210;
    background-color: transparent;

    grid-column-start: 4;
    grid-column-end: 5;
    grid-row-start: 4;
    grid-row-end: 5;
}
#btn-MenuIconSC:hover div svg g path{
    fill: #252525;
}
#btn-MenuIconSC:hover div p{
    color: #252525;
}
#description{
    position: absolute;
    float: right;
    width: 100%;
    height: 48px;
    z-index: 205;
    background-color: transparent;

    grid-column-start: 2;
    grid-column-end: 7;
    grid-row-start: 6;
    grid-row-end: 7;

    display: flex;
    flex-flow: column wrap;
    justify-content: center;
}

path{
    fill: #0078d7;
    transition: .2s;
}
p{
    margin: 0px;
    font-family: 'Titillium Web';
    font-size: 16px;
    color: #0078d7;
    transition: .2s;
    width: 100%;
    text-align: center;
}
</style>
