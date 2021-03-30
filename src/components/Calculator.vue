<template>
  <div class="bg">
    <Monitor v-bind:result="result"/>
    <SymbolPanel
        @PrintNum="printNum"
        @Clear="clear"
        @Compute="compute"
        @Prozent="prozent"
        @ChangeSign="changeSign"
    />
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
  methods: {
    clear(e) {
      console.log('Clear')
      this.result = e
    },

    compute() {
      this.result = (eval(this.result)).toString();
    },

    printNum(char) {
      if (this.result.length < 84) {
        if (char === "+" || char === "-" ||
            char === "*" || char === "/" || char === ".") {
          if (this.result[this.result.length - 1] !== "+" &&
              this.result[this.result.length - 1] !== "-" &&
              this.result[this.result.length - 1] !== "*" &&
              this.result[this.result.length - 1] !== "/" &&
              this.result[this.result.length - 1] !== ".") {
            if (this.checkTwopoint(char))
              this.result += char;
          }
        } else if (this.checkForZero()) {
          if (this.checkTwopoint("."))
            this.result = this.setCharAt(this.result, this.result.length - 1, char);
          else this.result += char;
        } else if ((this.result === "0") && char !== "." && char !== "/" && char !== "*")
          this.result = char
        else this.result += char;

        this.returnResult
      }
    },

    setCharAt(str, index, chr) {
      if (index > str.length - 1) return str;
      return str.substr(0, index) + chr + str.substr(index + 1);
    },

    checkTwopoint(char) {
      if (char === ".") {
        for (let i = this.result.length - 1; i > 0; i--) {
          if (this.result[i] === ".") {
            return false;
          }
          if (this.result[i] === "+" || this.result[i] === "-" || this.result[i] === "*" ||
              this.result[i] === "/") {
            return true;
          }
        }
      }
      return true;
    },

    checkForZero() {
      if (this.result.substring(this.result.lastIndexOf("+"))[1] === "0" && this.result.lastIndexOf("+") !== -1 ||
          this.result.substring(this.result.lastIndexOf("-"))[1] === "0" && this.result.lastIndexOf("-") !== -1 ||
          this.result.substring(this.result.lastIndexOf("*"))[1] === "0" && this.result.lastIndexOf("*") !== -1 ||
          this.result.substring(this.result.lastIndexOf("/"))[1] === "0" && this.result.lastIndexOf("/") !== -1) {
        return true;
      } else false;
    },
    prozent() {
      let re = /['+'\-'*'\\/]/;
      let chis = this.result.split(re);
      let re2 = /\d+/;
      let newList = this.result.split(re2);
      // eslint-disable-next-line use-isnan
      newList = newList.filter(op => op !== "" && op !== NaN);
      // eslint-disable-next-line use-isnan
      chis = chis.filter(num => num !== "" && num !== NaN);
      let percent = parseFloat(chis[0]) * (parseFloat(chis[1]) / 100);
      let result = 0;
      switch (newList[0]) {
        case "+": result = parseFloat(chis[0]) + percent; break;
        case "-": result = parseFloat(chis[0]) - percent; break;
        case "*": result = percent; break;
        case "/": result = parseFloat(chis[0]) / (parseFloat(chis[1]) / 100); break;
      }
      this.clear('');
      this.result += result;
    },

    changeSign() {
      let re = /['+'\-'*'\\/]/;
      let chis = this.result.split(re);
      let re2 = /\d+/;
      let newList = this.result.split(re2);
      // eslint-disable-next-line use-isnan
      chis = chis.filter(num => num !== "" && num != NaN);
      newList = newList.filter(char =>char !==".");

      switch (newList[newList.length - 2][0]) {
        case "+" : newList[newList.length - 2] = "-"; break;
        case "-" : newList[newList.length - 2] = "+"; break;
        case "*": case "/" : {
          if (newList[newList.length - 2] === "*-" || newList[newList.length - 2] === "/-") {
            newList[newList.length - 2] = newList[newList.length - 2][0];
          } else {
            chis[chis.length - 1] = (eval(chis[chis.length - 1] + "*-1")).toString();
          }
          break;
        }
        default: newList[0] = '-'; break;
      }
      this.clear('');
      for (let i = 0; i < newList.length; i++) {
        if (newList[i] !== "" || newList[i] !== null) {
          this.result += newList[i];
        }
        if (chis[i] != null)
          this.result += chis[i]
      }
    }
  },
  computed: {
    returnResult() {
      return this.result
    }
  }
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
