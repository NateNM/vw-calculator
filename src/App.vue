<template>
  <div id="calc">
    <div class="screen-sec">
      <div class="screen-text">SHARP est2024</div>
      <div class="screen-monitor">{{ screen }}</div>
    </div>
    <div class="btn num" @click="appendToScreen('7')">7</div>
    <div class="btn num" @click="appendToScreen('8')">8</div>
    <div class="btn num" @click="appendToScreen('9')">9</div>
    <div class="btn clear" @click="clearScreen">C</div>
    <div class="btn num" @click="appendToScreen('4')">4</div>
    <div class="btn num" @click="appendToScreen('5')">5</div>
    <div class="btn num" @click="appendToScreen('6')">6</div>
    <div class="btn" @click="appendToScreen('/')">/</div>
    <div class="btn num" @click="appendToScreen('1')">1</div>
    <div class="btn num" @click="appendToScreen('2')">2</div>
    <div class="btn num" @click="appendToScreen('3')">3</div>
    <div class="btn" @click="appendToScreen('*')">*</div>
    <div class="btn num" @click="appendToScreen('0')">0</div>
    <div class="btn" @click="appendToScreen('+')">+</div>
    <div class="btn" @click="appendToScreen('-')">-</div>
    <div class="btn equal" @click="calculate">=</div>
  </div>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';

@Options({})
export default class App extends Vue {
  screen = ('0');

  appendToScreen(char: string) {
    if (this.screen === '0') {
      this.screen = char;
    } else {
      this.screen += char;
    }
  }

  clearScreen() {
    this.screen = '0';
  }

  calculate() {
    try {
      console.log(eval(this.screen))
      this.screen = eval(this.screen);
      
    } catch (error) {
      this.screen = 'Error';
    }
  }
}

</script>

<style>
@import url('https://fonts.cdnfonts.com/css/calculator');

#calc{
  border: 2px solid black;
  width: 350px;
  height: 600px;
  margin: 0 auto;
  border-radius: 5px;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  background: linear-gradient(145deg, #d3cfc9, #e8e4e1);
  /* border-top-left-radius: 20px;
  border-top-right-radius: 20px; */
  border-radius: 20px 20px 20px 20px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.5);
  padding: 0 25px;
  padding-bottom: 30px;
  box-shadow: 10px 10px 20px rgba(0, 0, 0, 0.6), -10px -10px 20px rgba(255, 255, 255, 0.5);

}

.screen-sec{
  width: 100%;
  /* height: 20%; */
  /* background-color: wheat; */
  color: black;
  font-size: 80px;
  padding-top: 20%;
  padding-right: 15px;
  padding-left: 15px;
}

.screen-monitor{
  border: 2px solid black;
  height: 100px;
  border-radius: 10px;
  font-family: 'Calculator', sans-serif;
  background-color: #D6EDEF;
  font-size: 100px;
  padding-bottom: 10px;
  padding-top: 10px;
  margin-top: 0%;
  text-align: right;

}

.screen-text{
  font-size: large;
  font-weight: bold;
  padding-bottom: 5px;
  color: rgb(180, 64, 64);
  
}

.btn {
  width: 21%;
  text-align: center;
  color: black;
  background-color: #8E8B89;
  border-radius: 10%;
  cursor: pointer;
  margin: 4px;
  display: flex;
  flex-direction: column;
  align-content: center;
  justify-content: center;
  padding-top: 5px;
  padding-bottom: 5px;
  border: black solid;
  font-size: 30px; /* Adjust font size */
  font-family: Verdana, Geneva, Tahoma, sans-serif;
  font-weight: bold; /* Adjust font weight */
  box-shadow: 5px 5px 10px rgba(0, 0, 0, 0.2), -5px -5px 10px rgba(255, 255, 255, 0.5);

}

.btn:hover {
  opacity: 0.8;
}


.clear {
  background-color: #db5856;
}
</style>
