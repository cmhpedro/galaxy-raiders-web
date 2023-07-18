<template>
  <div id="canvas">
    <div id="deep-space" />
    <div id="menu" v-if="playable">
      <h1 class="title">Galaxy Raiders</h1>
      <button><router-link to="/game">Iniciar partida</router-link></button>
      <button><router-link to="/leaderboard">Placar</router-link></button>
      <button @click="closeGame">Sair</button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      playable: true
    };
  },
  methods: {
    closeGame() {
      this.playable = false;
    }
  }
};
</script>

<style>
#canvas {
  height: calc(100vh - 4rem);
  width: calc(100vw - 4rem);

  padding: 2rem;

  background-color: #36bbf5;
  overflow: hidden;

  position: relative;

  display: flex;
  justify-content: center;
  align-items: center;
}

@keyframes slide {
  0% {
    transform: translate(1px);
  }
  50% {
    transform: translate(-1px);
  }
  100% {
    transform: translate(1px);
  }
}

#deep-space {
  height: calc(100% - 4rem);
  width: calc(100% - 4rem);

  background-image: url("~/assets/space.png");
  background-origin: content-box;
  animation: slide 3s linear infinite;

  position: absolute;
  z-index: 0;
}

#menu {
  height: calc(100% - 4rem);
  width: calc(100% - 4rem);

  color: #36bbf5;

  position: relative;

  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  gap: 10%;
}

.title {
  color: #fff;

  font-size: 6rem;
  font-weight: bold;
  text-transform: uppercase;
}

button {
  height: 5%;
  width: 15%;

  color: #36bbf5;
  border: 1px solid #36bbf5;
  border-radius: 5px;

  font-size: 1.5rem;
  font-weight: bold;
  text-transform: uppercase;
}

button:hover {
  background-color: #36bbf5;
  color: #fff;
  border-radius: 5px;
  cursor: pointer;
}

</style>
