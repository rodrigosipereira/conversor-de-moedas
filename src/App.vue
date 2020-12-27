<template>
  <div id="app">
    <h1>Conversor de moedas</h1>
    <div class="linha">
      <Conversor moeda-a="USD" moeda-b="BRL"/>
    </div>
    <div class="linha">
      <Conversor moeda-a="BRL" moeda-b="USD"/>
    </div>
    <div class="linha">
      <Conversor moeda-a="CAD" moeda-b="BRL"/>
    </div>
    <div class="linha">
      <Conversor moeda-a="BRL" moeda-b="CAD"/>
    </div>
  </div>
</template>

<script>
import Conversor from "./components/Conversor.vue"
export default {
  name: 'App',
  components: {
    Conversor
  }
}
</script>

<style>
#app {
  margin: auto;
  max-width: 900px;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.linha{
  margin-top: 40px;
  margin-bottom: 40px;
  text-align: center;
  display: flex;
  justify-content: center;
}
</style>
