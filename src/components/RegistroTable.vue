<template>
  <div id="instanciasTableDiv">
    <table>
      <thead>
        <th id="headTable" colspan="5">{{lugarSeleccionado}} - Piso {{pisoSeleccionado}}</th>
      </thead>
      <tbody>
        <tr>
          <th>Sensor</th>
          <th>Valor</th>
          <th>Unidad de medida</th>
          <th colspan="2"></th>
        </tr>
        <tr id="registroRow" v-for="registro in registros" :key="registro.id">
          <td>{{ registro.valor }}</td>
          <td>{{ registro.fecha }}</td>
          <td>{{ registro.frecuencia }}</td>
          <td id="imgModificar">
            <button type="button" data-bs-toggle="modal" data-bs-target="#exampleModal">
              <img src="../assets/modificar.png" />
            </button>
            
          </td>
          <td id="imgTacho">
            <button>
              <img src="../assets/tacho.png" />
            </button>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
import registros from "@/registros.json";

export default {
  name: "RegistroTable",
  props: {
    lugarSeleccionado:String,
    pisoSeleccionado:Number
  },
  data() {
    return {
      registros
    };
  },
};
</script>

<style scoped>
#instanciasTableDiv {
  margin-top: 10px;
  display: flex;
  justify-content: center;
  flex-direction: row;
  padding: 10px 0;
}

table {
  font-family: sans-serif;
  width: 90%;
}

td,
th {
  border-color: black;
  border-style: groove;
  border-width: 1px;
}

th {
  font-family: sans-serif;
  margin: 0px auto;
  padding: 10px;
  text-align: left;
  width: 30%;
  background: #1b9752;
  color: white;
  font-weight: 400;
}

td {
  background: none;
  padding-left: 10px;
}

#headTable {
  text-align: center;
}

#registroRow {
  margin: 0px auto;
  text-align: left;
  width: 33%;
  font-family: consolas;
  font-weight: 400;
  color: black;
}

#registroRow:hover {
  background: #1b9752;
  color: white;
}

img {
  width: 32px;
  height: 32px;
  align-content: center;
}

#imgTacho,
#imgModificar {
  width: 5%;
  align-items: center;
}

#imgTacho button,
#imgModificar button{
  border: none;
  background: transparent;
}

</style>