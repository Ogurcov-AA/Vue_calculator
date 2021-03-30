<template>
  <div class="line">
    <div class="line1H">
      <hr>
    </div>
    <div class="line2H">
      <hr>
    </div>
    <div class="line3H">
      <hr>
    </div>
    <div class="line4H">
      <hr>
    </div>
    <div class="line5H">
      <hr>
    </div>
    <hr class="line1V">
    <hr class="line2V">
    <hr class="line3V">
  </div>
</template>

<style scoped>
.line {
  position: absolute;
  width: 415px;
  height: 530px;
  left: -1px;
  bottom: 2px;
}

hr {
  mix-blend-mode: normal;
  opacity: 0.1;
  border: 1px solid #FFFFFF;
}

.line5H {
  position: absolute;
  width: 415px;
  left: 0px;
  top: 416px;

}

.line4H {
  position: absolute;
  width: 415px;
  left: 0px;
  top: 312px;

}

.line3H {
  position: absolute;
  width: 415px;
  left: 0px;
  top: 208px;
}

.line2H {
  position: absolute;
  width: 415px;
  left: 0px;
  top: 100px;
}

.line1H {
  position: absolute;
  width: 415px;
  left: 0px;
  top: 0px;
}

.line1V {
  position: absolute;
  height: 415px;
  left: 103.5px;
  top: 1.5px;

}

.line2V {
  position: absolute;
  height: 528.51px;
  left: 208px;
  top: 1px;

}

.line3V {
  position: absolute;
  height: 519.01px;
  left: 311.5px;
  top: 1.5px;

}
</style>
