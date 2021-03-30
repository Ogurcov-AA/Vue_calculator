<template>
  <div class="bg">
    <Monitor/>
    <SymbolPanel/>
  </div>
</template>

<script>

import Monitor from "@/components/Monitor";
import SymbolPanel from "@/components/SymbolPanel";

export default {
  components: {
    Monitor,
    SymbolPanel
  },
  data() {
    return {
      result: '0'
    }
  },
  methods: {}

}
</script>

<style>
.bg {

  position: absolute;
  width: 414px;
  height: 740px;
  left: calc(50% - 414px / 2);
  top: -3px;
  margin-top: 60px;

  background: linear-gradient(180deg, #F2736E -24.93%, #F04949 96.2%);

}
</style>
