<template>
  <div class="line">
    <div class="line1H">
      <hr>
      <SymbolButton v-bind:value='"C"'
                    v-bind:shadow=true
                    v-bind:style="{left:1+'px',top:9+'px'}"
      />

      <SymbolButton v-bind:value='"+/-"'
                    v-bind:shadow=true
                    v-bind:style="{  left: 106 + 'px',top:9+'px'}"
      />

      <SymbolButton v-bind:value='"%"'
                    v-bind:shadow=true
                    v-bind:style="{  left: 210 + 'px',top:9+'px'}"
      />
      <SymbolButton v-bind:value='"/"'
                    v-bind:style="{  left: 314 + 'px',top:9+'px'}"
                    @click.native="printNum('/')"
      />
    </div>
    <div class="line2H">
      <hr>
      <SymbolButton v-bind:value="7"
                    v-bind:style="{left:1+'px',top:9+'px'}"
                    @click.native="printNum('7')"
      />

      <SymbolButton v-bind:value="8"
                    v-bind:style="{  left: 106 + 'px',top:9+'px'}"
                    @click.native="printNum('8')"
      />

      <SymbolButton v-bind:value="9"
                    v-bind:style="{  left: 210 + 'px',top:9+'px'}"
                    @click.native="printNum('9')"
      />
      <SymbolButton v-bind:value='"x"'
                    v-bind:style="{  left: 314 + 'px',top:9+'px'}"
                    @click.native="printNum('*')"
      />
    </div>
    <div class="line3H">
      <hr>
      <SymbolButton v-bind:value="4"
                    v-bind:style="{left:1+'px',top:9+'px'}"
                    @click.native="printNum('4')"
      />

      <SymbolButton v-bind:value="5"
                    v-bind:style="{  left: 106 + 'px',top:9+'px'}"
                    @click.native="printNum('5')"
      />

      <SymbolButton v-bind:value="6"
                    v-bind:style="{  left: 210 + 'px',top:9+'px'}"
                    @click.native="printNum('6')"
      />
      <SymbolButton v-bind:value='"-"'
                    v-bind:style="{  left: 314 + 'px',top:9+'px'}"
                    @click.native="printNum('-')"
      />
    </div>
    <div class="line4H">
      <hr>
      <SymbolButton v-bind:value="1"
                    v-bind:style="{left:1+'px',top:9+'px'}"
                    @click.native="printNum('1')"
      />

      <SymbolButton v-bind:value="2"
                    v-bind:style="{  left: 106 + 'px',top:9+'px'}"
                    @click.native="printNum('2')"
      />

      <SymbolButton v-bind:value="3"
                    v-bind:style="{  left: 210 + 'px',top:9+'px'}"
                    @click.native="printNum('3')"
      />
      <SymbolButton v-bind:value='"+"'
                    v-bind:style="{  left: 314 + 'px',top:9+'px'}"
                    @click.native="printNum('+')"
      />
    </div>
    <div class="line5H">
      <hr>
      <SymbolButton v-bind:value="0"
                    v-bind:doubleCell="true"
                    v-bind:style="{left: 0+'px',top:9+'px'}"
                    @click.native="printNum('0')"
      />

      <SymbolButton v-bind:value='"."'
                    v-bind:style="{  left: 210 + 'px',top:9+'px'}"
                    @click.native="printNum('.')"
      />
      <SymbolButton v-bind:value='"="'
                    v-bind:pickout=true
                    v-bind:style="{  left: 312 + 'px',top:10+'px'}"
      />
    </div>
    <hr class="line1V">
    <hr class="line2V">
    <hr class="line3V">
  </div>
</template>


<script>
import SymbolButton from '@/components/SymbolButton'


export default {
  components: {
    SymbolButton
  },
  methods: {
    printNum(e) {
      this.$emit('PrintNum', e);
    }
  }
}
</script>

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
