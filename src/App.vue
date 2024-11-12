<template>
  <div id="app">
    <header>
      <h1>Bit-Game Store</h1>
    </header>
    
    <!-- Mensaje de bienvenida -->
    <section class="welcome-message">
      <h3>¡Bienvenidx a Bit-Game Store!</h3>
      <p>A continuación puedes ver y gestionar tus juegos preferidos.</p>
    </section>

    <!-- Componente GameList como tabla -->
    <section class="game-list-section">
      <GameList :games="games" @delete-game="removeGame" />
    </section>
    
    <!-- Footer de la página -->
    <footer>
      <p>&copy; 2024 Bit-Game Store. Todos los derechos reservados.</p>
    </footer>
  </div>
</template>

<script>
import GameList from './components/GameList.vue';

export default {
  name: 'App',
  components: {
    GameList
  },
  data() {
    return {
      games: ["Arena of valor", "Pokemon Unite", "Donkey Kong", "Heroes of the storm", "Valorant"]
    };
  },
  methods: {
    removeGame(index) {
      this.games.splice(index, 1);
    }
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
/*   -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px; */
}
body {
  margin: 0;
  min-height: 100vh;
}
header {
  margin: 0;
  background-color: #4CAF50;
  color: white;
  padding: 15px;
  text-align: center;
}
.welcome-message {
  text-align: left;
  margin: 20px;
}
.game-list-section {
  display: flex;
  justify-content: center;
  margin: 20px;
}
footer {
  background-color: #333;
  color: white;
  text-align: center;
  padding: 10px;
  position: fixed;
  bottom: 0;
  width: 100%;
}
</style>
