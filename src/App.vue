<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <component :is="chart"></component>

    <button @click="switchToXY">XY</button>
    <button @click="switchToRadar">Radar</button>
  </div>
</template>

<script>
import XY from './components/charts/XY.vue'
import Radar from './components/charts/Radar.vue'

export default {
    data: function () {
        return{
            chart: "XY"
        }
    },
    methods: {
        switchToXY: function () {
            this.chart = "XY"
        },
        switchToRadar: function () {
            this.chart = "Radar"
        }
    },
    name: 'app',
    components: {
        XY, Radar
    }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
