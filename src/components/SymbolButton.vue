<template>
  <div style="position: absolute" v-if="shadow">
    <button style="mix-blend-mode: normal; opacity: 0.5">{{ value }}</button>
  </div>
  <div style="position: absolute" v-else-if="pickout">
    <div class="rectangle">
      <button>{{ value }}</button>
    </div>
  </div>
  <div v-else-if="doubleCell">
    <button style="width: 204px;display: flex">{{ value }}</button>
  </div>
  <div style="position: absolute" v-else>
    <button>{{ value }}</button>
  </div>
</template>

<script>
export default {
  name: "SymbolButton",
  props: ["value", "shadow", "pickout", "doubleCell"]
}
</script>

<style scoped>
button {

  background: transparent;
  border: 0;
  width: 100px;
  height: 100px;
  font-size: 30px;
  justify-content: center;
  font-family: Actor, sans-serif;
  font-style: normal;
  font-weight: normal;
  line-height: 36px;
  align-items: center;
  color: #FFFFFF;
  outline: none;
}

.rectangle {

  position: absolute;
  width: 103px;
  height: 103.5px;

  background: #E33D3D;

}

</style>
