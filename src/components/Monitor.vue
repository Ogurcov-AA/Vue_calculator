<template>
  <div class="BgMonitor">
    <div class="p">
      <p>{{checkResult()}}</p>
    </div>
  </div>
</template>

<script>

export default {
  props: ['result'],
  methods: {
    checkResult() {
      let fontSize = document.styleSheets[0].cssRules[0].style.cssText.match(/(font-size: \d+)/);
      console.log(fontSize[0].toString());
      let size = fontSize[0].split(' ')[1];
      let newSize = size;
      if(this.result.length===1){
        newSize=72;
      }
      if(this.result.length<25 && this.result.length!==1) {
        newSize = 72 - this.result.length;
      }
      else if(this.result.length>43 && this.result.length<59){
        newSize-=1;
      }
      document.styleSheets[0].cssRules[0].style.cssText = document.styleSheets[0].cssRules[0].style.cssText.replace("font-size: "+size + "px","font-size: " + newSize + "px");
      return this.result
    }
  }
}
</script>

<style scoped>
.p{
  font-family: Roboto , monospace;
  height: 218.5px;
  font-size: 72px;
  word-break: break-all;

  text-align: center;
  color: #FFFFFF;
}

.BgMonitor {
  position: absolute;
  width: 414px;
  height: 218.5px;
  left: calc(50% - 414px/2);
  top: -3px;
  text-overflow: clip;
  background: linear-gradient(180deg, #2C3059 22.08%, #393E73 112.93%);
}




</style>
