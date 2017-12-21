<template>
  <div id="btnMenuIconWD" class="content" @click="click">
    <div class="btn" v-bind:class="{btnSelected:isSelected}"></div>
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
  name: "btnMenuIconWD",
  props:[
      'description', 'data', 'event', 'isSelected'
  ],
  methods: {
      click(){
        EventBus.$emit('Suite-Menu-SelectModule', this.description);
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
    width: 100%;
    height: 72px;
    z-index: 201;
    background-color: transparent;
    grid-template-columns: 72px 12px 1fr;
    grid-template-rows: 72px;
}

.btn{
    grid-row-start: 1;
    grid-row-end: 2;
    grid-column-start: 1;
    height: 48px;
    width: 8px;
    margin: 12px 0px 12px 0px;
    background-color: transparent;
    z-index: 205;
    position: absolute;
}
.btnSelected{
    background-color: #0078d7;
}

#icon{
    position: absolute;
    width: 24px;
    height: 24px;
    margin: 24px;
    z-index: 210;
    background-color: transparent;

    grid-column-start: 1;
    grid-column-end: 2;
    grid-row-start: 1;
    grid-row-end: 2;
}
#btnMenuIconWD:hover div svg g path{
    fill: #0078d7;
}
#btnMenuIconWD:hover div p{
    color: #0078d7;
}
#description{
    position: absolute;
    float: right;
    width: auto;
    height: 72px;
    z-index: 205;
    background-color: transparent;

    grid-column-start: 3;
    grid-column-end: 4;
    grid-row-start: 1;
    grid-row-end: 2;

    display: flex;
    flex-flow: column wrap;
    justify-content: center;
}

path{
    fill: #252525;
}
p{
    margin: 0px;
    font-family: 'Titillium Web';
    font-size: 16px;
    color: #252525;
}
</style>
