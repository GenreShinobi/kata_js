<template>
  <div id="app">
    <h1>Code Kata Ninja</h1>
    <Katas/>
  </div>
</template>

<script>
import Katas from "@/components/Katas";

export default {
  name: 'app',
  components: {
    Katas
  }
}
</script>

<style>
  html {
    background: #282c34;
  }
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: white;
    margin-top: 60px;
  }
  button:focus {
    outline: none;
  }
  input:focus {
    outline: none;
  }
</style>
