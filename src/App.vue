<template>
  <p></p>
  <app-to-do-card>

  </app-to-do-card>
</template>

<script>
import AppToDoCard from "./components/AppToDoCard";

export default {
  name: 'App',
  components: {AppToDoCard}
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
body {
  width: 100%;
  min-height: 100vh;
  margin: 0;
  padding: 16px;
  display: flex;
  justify-content: center;
  align-items: center;
  background-image: linear-gradient(62deg, rgba(1, 95, 183, 0.9732216701223994) 13%, rgba(255, 122, 151, 0.5) 4%),
  linear-gradient(44deg, rgba(0, 43, 99, 0.07922090238615942) 39%, rgba(242, 140, 143, 0.5) 18%),
  linear-gradient(118deg, rgba(84, 202, 242, 0.03152997265339608) 40%, rgba(247, 155, 187, 0.5) 54%),
  linear-gradient(58deg, rgba(90, 90, 237, 0.16144443572260592) 83%, rgba(249, 156, 142, 0.5) 23%);
  background-blend-mode: normal,lighten,multiply,hard-light;
  font-family: 'DM Sans', sans-serif;
}

* {
  box-sizing: border-box;
}

label {
  display: flex;
  align-items: flex-start;
  color: #fff;
  margin-right: 8px;
  font-size: 14px;
  line-height: 24px;
  position: relative;
  transition: .2s;
  cursor: pointer;
}
</style>
