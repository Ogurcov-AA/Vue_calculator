<template>
  <div class="BgMonitor">
    <div class="p">
      <p>{{result}}</p>
    </div>
  </div>
</template>

<script>

export default {
  props: ['result']

}
</script>

<style scoped>

.BgMonitor {
  position: absolute;
  width: 414px;
  height: 218.5px;
  left: calc(50% - 414px / 2);
  top: -3px;
  text-overflow: clip;
  background: linear-gradient(180deg, #2C3059 22.08%, #393E73 112.93%);
}

.p {
  font-family: Roboto, monospace;
  height: 218.5px;
  font-size: 72px;
  word-break: break-all;

  text-align: center;
  color: #FFFFFF;
}


</style>
