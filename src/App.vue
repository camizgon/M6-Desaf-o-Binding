<template>
  <div id="app">
    <form>
      <div>
        <label for="cardTitle">Título de la tarjeta: </label>
        <input id="cardTitle" v-model="card.title" />
      </div>

      <div>
        <label for="chipSrc">Chip SRC: </label>
        <input id="chipSrc" v-model="card.chipSrc" />
      </div>

      <div>
        <label for="cardNumber">Número: </label>
        <input id="cardNumber" v-model="card.number" />
      </div>

      <div>
        <label for="expiryDate">Fecha de expiración: </label>
        <input id="expiryDate" v-model="card.expiryDate" />
      </div>

      <div>
        <label for="cardOwner">Propietario: </label>
        <input id="cardOwner" v-model="card.owner" />
      </div>

      <div>
        <label for="cardTypeSrc">Tipo de tarjeta SRC: </label>
        <input id="cardTypeSrc" v-model="card.typeSrc" />
      </div>
    </form>

    <div class="card">
      <h3>{{ card.title }}</h3>
      <img :src="card.chipSrc" width="40" alt="chip" />
      <div>
        <h2>{{ card.number }}</h2>
        <span>Fecha Exp: <b>{{ card.expiryDate }}</b></span>
      </div>
      <footer>
        <span>{{ card.owner }}</span>
        <img :src="card.typeSrc" width="60" alt="card type" />
      </footer>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      card: {
        title: '',
        chipSrc: '',
        number: '',
        expiryDate: '',
        owner: '',
        typeSrc: '',
      },
    };
  },
};
</script>

<style>
* {
  margin: 0;
}
body {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  font-size: 10px;
  font-family: sans-serif;
}

#app {
  display: flex;
  gap: 40px;
}
form {
  padding: 18px;
  border-radius: 20px;
  border: ridge 1px;
  box-shadow: 1px 1px 1px 1px gray;
  font-weight: bold;
  display: flex;
  flex-direction: column;
  gap: 15px;
  justify-content: center;
}
form div {
  display: grid;
  grid-template-columns: 100px 200px;
  align-items: center;
  gap: 5px;
}

form div label {
  text-align: right;
}

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

h3 {
  font-size: 20px;
}

h2 {
  font-size: 30px;
  letter-spacing: 10px;
  margin-bottom: 15px;
  text-shadow: 0px 0px 1px gold;
  font-family: Times;
}

b {
  font-size: 16px;
}

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

