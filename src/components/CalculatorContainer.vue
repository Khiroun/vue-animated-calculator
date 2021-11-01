<template>
  <div class="container">
    <form action="#" name="forms">
      <input type="text" v-model="inputString" />
      <div class="buttons">
        <input type="button" value="AC" @click="clearInput" />
        <input type="button" value="DEL" @click="del" />
        <InputButton value="%" @update-value="updateInputString" />
        <InputButton value="/" @update-value="updateInputString" />
      </div>
      <div class="buttons">
        <InputButton value="7" @update-value="updateInputString" />
        <InputButton value="8" @update-value="updateInputString" />
        <InputButton value="9" @update-value="updateInputString" />
        <InputButton value="*" @update-value="updateInputString" />
      </div>
      <div class="buttons">
        <InputButton value="4" @update-value="updateInputString" />
        <InputButton value="5" @update-value="updateInputString" />
        <InputButton value="6" @update-value="updateInputString" />
        <InputButton value="-" @update-value="updateInputString" />
      </div>
      <div class="buttons">
        <InputButton value="1" @update-value="updateInputString" />
        <InputButton value="2" @update-value="updateInputString" />
        <InputButton value="3" @update-value="updateInputString" />
        <InputButton value="+" @update-value="updateInputString" />
      </div>
      <div class="buttons">
        <InputButton value="0" @update-value="updateInputString" />
        <InputButton value="00" @update-value="updateInputString" />
        <InputButton value="." @update-value="updateInputString" />

        <input type="button" value="=" @click="computeResult" />
      </div>
    </form>
  </div>
</template>

<script>
import InputButton from "./InputButton.vue";
export default {
  name: "CalculatorContainer",
  components: {
    InputButton,
  },
  data() {
    return {
      inputString: "",
    };
  },
  methods: {
    updateInputString(str) {
      this.inputString = this.inputString + str;
    },
    computeResult() {
      this.inputString = eval(this.inputString);
    },
    clearInput() {
      this.inputString = "";
    },
    del() {
      this.inputString = this.inputString.substr(
        0,
        this.inputString.length - 1
      );
    },
  },
};
</script>
<style>
.container {
  z-index: 12;
  width: 360px;
  padding: 15px;
  border-radius: 12px;
  background: rgba(255, 255, 255, 0.1);
  box-shadow: 0 20px 50px rgba(0, 0, 0, 0.15);
  border-top: 1px solid rgba(255, 255, 255, 0.5);
  border-left: 1px solid rgba(255, 255, 255, 0.5);
}
.container input[type="text"] {
  width: 100%;
  height: 100px;
  margin: 0 3px;
  outline: none;
  border: none;
  color: #fff;
  font-size: 20px;
  text-align: right;
  padding-right: 10px;
  pointer-events: none;
  background: transparent;
}
.container input[type="button"] {
  height: 65px;
  color: #fff;
  width: calc(100% / 4 - 5px);
  background: transparent;
  border-radius: 12px;
  margin-top: 15px;
  outline: none;
  border: none;
  font-size: 20px;
  cursor: pointer;
  transition: all 0.3s ease;
}
.container input[type="button"]:hover {
  background: rgba(255, 255, 255, 0.1);
}
</style>
