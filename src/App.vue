<template>
  <div id="app">
    <!-- Formulario para ingresar los datos de la tarjeta -->
    <form>
      <!-- Campo para el título de la tarjeta -->
      <div>
        <label for="cardTitle">Título de la tarjeta: </label>
        <input id="cardTitle" v-model="card.title" />
      </div>

      <!-- Campo para la fuente del chip de la tarjeta -->
      <div>
        <label for="chipSrc">Chip SRC: </label>
        <input id="chipSrc" v-model="card.chipSrc" />
      </div>

      <!-- Campo para el número de la tarjeta -->
      <div>
        <label for="cardNumber">Número: </label>
        <input id="cardNumber" v-model="card.number" />
      </div>

      <!-- Campo para la fecha de expiración de la tarjeta -->
      <div>
        <label for="expiryDate">Fecha de expiración: </label>
        <input id="expiryDate" v-model="card.expiryDate" />
      </div>

      <!-- Campo para el propietario de la tarjeta -->
      <div>
        <label for="cardOwner">Propietario: </label>
        <input id="cardOwner" v-model="card.owner" />
      </div>

      <!-- Campo para la fuente del tipo de tarjeta -->
      <div>
        <label for="cardTypeSrc">Tipo de tarjeta SRC: </label>
        <input id="cardTypeSrc" v-model="card.typeSrc" />
      </div>
    </form>

    <!-- Sección para mostrar la tarjeta con los datos ingresados -->
    <div class="card">
      <!-- Título de la tarjeta -->
      <h3>{{ card.title }}</h3>
      <!-- Imagen del chip de la tarjeta -->
      <img :src="card.chipSrc" width="40" alt="chip" />
      <div>
        <!-- Número de la tarjeta -->
        <h2>{{ card.number }}</h2>
        <!-- Fecha de expiración de la tarjeta -->
        <span>Fecha Exp: <b>{{ card.expiryDate }}</b></span>
      </div>
      <footer>
        <!-- Nombre del propietario de la tarjeta -->
        <span>{{ card.owner }}</span>
        <!-- Imagen del tipo de tarjeta -->
        <img :src="card.typeSrc" width="60" alt="card type" />
      </footer>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      // Estado del componente con los datos de la tarjeta
      card: {
        title: '',
        chipSrc: '/chip.png', // Ruta predeterminada a la imagen chip.png
        number: '',
        expiryDate: '',
        owner: '',
        typeSrc: '/visa.png', // Ruta predeterminada a la imagen visa.png
      },
    };
  },
};
</script>

<style>
/* Estilos globales */
* {
  margin: 0;
}

/* Estilo del cuerpo del documento */
body {
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 10px;
  font-family: sans-serif;
}

/* Estilo del contenedor principal de la aplicación */
#app {
  display: flex;
  gap: 40px;
}

/* Estilo del formulario */
form {
  padding: 18px;
  border-radius: 20px;
  box-shadow: 1px 1px 1px 1px black;
  font-weight: bold;
  display: flex;
  flex-direction: column;
  gap: 15px;
  justify-content: center;
}


/* Estilo del contenedor de la tarjeta */
.card {
  width: 400px;
  height: 230px;
  background: #1c1a1e;
  color: white;
  border-radius: 20px;
  padding: 20px;
  box-shadow: 0px 0px 10px 2px black;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

/* Estilo del título de la tarjeta */
h3 {
  font-size: 20px;
}

/* Estilo del número de la tarjeta */
h2 {
  font-size: 30px;
  letter-spacing: 10px;
  margin-bottom: 15px;
  text-shadow: 0px 0px 1px gold;
  font-family: Times;
}

/* Estilo de la fecha de expiración */
b {
  font-size: 16px;
}

/* Estilo del pie de la tarjeta */
footer {
  display: flex;
  justify-content: space-between;
  align-items: flex-end;
  font-weight: bold;
  font-size: 18px;
  text-transform: uppercase;
  font-style: italic;
}
</style>

