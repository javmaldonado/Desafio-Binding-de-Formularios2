<template>
  <div>
    <form class="m-3">

      <label class="form-label">Titulo<input class="m-3" type="text" v-model="titulo" /></label>

      <hr>
      <div class=" m-3 mb-3">
        <label class="form-label">Emoji</label>
        <select class="form-select" v-model="emoji">
          <option value="👩🏻‍💻">👩🏻‍💻</option>
          <option value="🧑🏻‍💻">🧑🏻‍💻</option>
        </select>
      </div>
      <hr>
      <div>
        <label class="m-3">Apreciación:</label>
        <input type="radio" value="Regular" name="calificacion" v-model="calificacion" />
        Regular
        <input type="radio" value="Bien" name="calificacion" v-model="calificacion" />
        Bien
        <input type="radio" value="Muy bien" name="calificacion" v-model="calificacion" />
        Muy bien
        <input type="radio" value="Increible" name="calificacion" v-model="calificacion" />
        Increíble
      </div>
      <hr>
      <div class="mb-3">
        <label class="form-label m-3">Competencias aprendidas</label>
        <ul>
          <li>
            <input v-model="competencias" name="competencias" type="checkbox" value="Morfología de un componente" />
            Morfología de un componente
          </li>
          <li>
            <input v-model="competencias" name="competencias" type="checkbox" value="Directivas" />
            Directivas
          </li>
          <li>
            <input v-model="competencias" name="competencias" type="checkbox" value="One-Way y Two-Way data binding" />
            One-Way y Two-Way data binding
          </li>
          <li>
            <input v-model="competencias" name="competencias" type="checkbox" value="Estado" />
            Estado
          </li>
          <li>
            <input v-model="competencias" name="competencias" type="checkbox" value="Patrón de diseño MVVM" />
            Patrón de diseño MVVM
          </li>
        </ul>
      </div>
      <hr>
      <p class="m-3">Opinión:</p>
      <textarea class="m-3" v-model="opinion" placeholder="Escribe tu opinión..."></textarea>
    </form>
  </div>


  <div class="container ">
    <h2>{{ emoji }}</h2>
    <h3>{{ titulo }}</h3>
    <div>
      <span><b>Y me parece,</b> {{ calificacion }}</span>
    </div>
    <div>
      <span><b>He aprendido:</b><br>{{ competencias.join(', ') }}</span>
      <br>
      <p><b>Mi opinion hasta ahora:</b> <br>{{ opinion }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'BindingForms2',
  data() {
    return {
      titulo: "",
      emoji: "",
      calificacion: "",
      competencias: [],
      opinion: ""
    };
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  display: flex;
  gap: 40px;
  color: #2c3e50;
}

form {
  padding: 18px;
  border-radius: 20px;
  border: ridge 1px;
  background-color: black;
  color: white;
  font-weight: bold;
  display: flex;
  flex-direction: column;
  gap: 15px;
  justify-content: center;
}

li {
  list-style: none;
}

.container {
  padding: 18px;
  border-radius: 20px;
  border: ridge 1px;
  margin: 1rem;

  text-align: center;
  display: flex;
  flex-direction: column;
  gap: 15px;
  align-items: center;
  font-weight: bold;
  float: right;
  width: 50%;



}


.container span,
.container p {
  display: block;

}
</style>
