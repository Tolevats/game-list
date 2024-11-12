<template>
  <div>
    <div class="content">
      <h2>Mis Favoritos</h2>
      <!-- Contenedor de desplazamiento para pantallas pequeñas -->
        <div class="table-container">
          <table>
            <thead>
              <tr>
                <th>#</th>
                <th>Juego</th>
                <th>Acción</th> 
              </tr>
            </thead> 
            <tbody>
                <tr v-for="(game, index) in games" :key="index">
                    <td>{{ index + 1 }}</td>
                    <td>{{ game }}</td>
                    <td><button @click="deleteGame(index)">Eliminar</button></td>
                </tr>
            </tbody> 
          </table>
        </div>  
    </div>
    
  </div>
</template>

<script>
export default {
    name: 'GameList',
    props: {
        games: Array
    },
    /* data: function(){
        return {}
    }, */
    // computed: {},
    methods: {
        deleteGame(index) {
            this.$emit("delete-game", index);
        }
    }
    // watch: {},
    // components: {},
    // mixins: [],
    // filters: {},
    // -- Lifecycle Methods
    // -- End Lifecycle Methods
};
</script>

<style scoped>
/* padding de contenido para evitar overlap del footer */
.content {
  padding-bottom: 60px;
}
h2 {
  text-align: center;
}
/* contenedor para hacer la tabla desplazable en pantallas pequeñas */
.table-container {
  max-height: 700px;
  overflow-y: auto;
  width: 100%;
}
table {
  width: 100%;
  margin: 0 auto;
  border-collapse: collapse;
}
th, td {
  padding: 10px;
  text-align: left;
  border: 1px solid #ddd;
}
th {
  background-color: #f4f4f4;
}
/* Asegurar que la columna de "Juego" sea más larga */
th:nth-child(2),
td:nth-child(2) {
  min-width: 300px;
}
button {
  background-color: #fc7d7d;
  color: white;
  padding: 5px 10px;
  cursor: pointer;
  border: none;
  border-radius: 4px;
}
button:hover {
  background-color: #ff3333;
}
</style>