<template>
    <div>
      Hi
    </div>
</template>

<script>
import Block from "./core/Block"
import Blockchain from "./core/Blockchain"

export default {
  name: 'App',
  mounted(){
    this.initCrypto()
  },
  methods:{
    initCrypto(){
      let smashingCoin = new Blockchain();

      console.log("smashingCoin mining in progress....");
      smashingCoin.addNewBlock(
        new Block(1, "01/06/2020", {
          sender: "Iris Ljesnjanin",
          recipient: "Cosima Mielke",
          quantity: 50
        })
      );

      smashingCoin.addNewBlock(
        new Block(2, "01/07/2020", {
          sender: "Vitaly Friedman",
          recipient: "Ricardo Gimenes",
          quantity: 100
        })
      );
      console.log(smashingCoin.checkChainValidity())
      console.log(JSON.stringify(smashingCoin, null, 4));
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
