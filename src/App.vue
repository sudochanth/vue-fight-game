<template>
  <div id="app">
    <div class="players">
      <div class="you">
        <h1>you</h1>
        <div class="health-bar">100</div>
      </div>

      <div class="enemy">
        <h1>enemy</h1>
        <div class="health-bar">100</div>
      </div>
    </div>
    <div class="menu">
      <div class="start" @click="gameStart" v-if="!isStarted">
        <div>START</div>
      </div>
      
      <div v-else class="game-menu">
        <button class="attack">ATTACK</button>
        <button class="special-attack">SPECIAL ATTACK</button>
        <button class="heal">HEAL</button>
        <button class="surrender" @click="isStarted = !isStarted">SURRENDER</button>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  name: 'App',
  data() {
    return {
      isStarted: false
    }
  },
  methods: {
    gameStart() {
      this.isStarted = !this.isStarted
      console.log(this.isStarted)
    }
  }
}
</script>

<style>

  * {
    letter-spacing: 4px;
  }

  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }

  button {
    outline: none;
  }

  .players  {
    display: flex;
    justify-content: space-around;
    border: black 5px solid;
    padding: 5%;
  }

  .health-bar {
    background-color: green;
    color: white;
    width: 250px;
    padding: 5px;
    /*height: max-content;*/
  }

  .menu {
    display: flex;
    justify-content: center;
    margin-top: 50px;
  }
  .start {
    background-color: cornflowerblue;
    padding: 15px;
    width: 350px;
    color: white;
    border-radius: 15px;
    outline: none;
    box-shadow: 0 9px #999999;
    cursor: pointer;
  }

  .start:hover {
    background-color: royalblue;
  }

  .start:active {
    box-shadow: 0 5px #666;
    transform: translateY(4px);
  }

  button:active {
    box-shadow: 0 5px #666;
    transform: translateY(4px);
  }

  .game-menu {
    display: flex;
  }

  .game-menu button {
    margin: 20px;
    padding: 20px;
    border-radius: 15px;
    box-shadow: 0 5px #999999;
    font-size: medium;
  }

  .attack {
    background-color: indianred;
  }

  .special-attack {
    background-color: lightsalmon;
  }

  .heal {
    background-color: lightgreen;
  }

  .surrender {
    background-color: white;
  }
</style>
