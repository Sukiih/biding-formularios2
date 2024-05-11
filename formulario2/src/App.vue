<template>
  <div class="container">
    <div class="form-wrapper">
        <div class="form-field">
          <label for="titulo">Titulo:</label>
          <input v-model="titulo" 
          id="titulo" 
          type="text" 
          name="titulo" >
        </div>
        <hr>

        <div class="form-field">
          <label for="emojis">Emoji:</label>
          <select v-model="emoji" id="emojis" name="emojis" >
            <option value="👩🏻‍💻">👩🏻‍💻</option>
            <option value="🥴">🥴</option>
            <option value="💀">💀</option>
            <option value="😊">😊</option>
            <option value="🤩">🤩</option>
          </select>
        </div>

        <hr>

        <div class="form-field">
          <p class="form-title">Apreciación:</p>

          <div class="form-radio">
            <input v-model="apreciacion" type="radio" id="regular" name="apreciacion" value="Regular">
            <label for="regular">Regular</label>
          </div>
          
          <div class="form-radio">
            <input v-model="apreciacion" type="radio" id="bien" name="apreciacion" value="Bien">
            <label for="bien">Bien</label>
          </div>

          <div class="form-radio">
            <input v-model="apreciacion" type="radio" id="muyBien" name="apreciacion" value="Muy bien">
            <label for="muyBien">Muy bien</label>
          </div>

          <div class="form-radio">
            <input v-model="apreciacion" type="radio" id="increible" name="apreciacion" value="Increible">
            <label for="increible">Increible</label>
          </div>
        </div>
        <hr>

        <div class="form-field form--competencias">
          <p class="form-title">Competencias aprendidas:</p>

            <div class="form-checkbox">
              <div>
                <input v-model="competencias" type="checkbox" id="morfologia" name="morfologia" value="Morfología de un componente">
                <label for="morfologia">Morfología de un componente</label>
              </div>

              <div>
                <input v-model="competencias" type="checkbox" id="biding" name="biding" value="One-Way y Two-Way data binding">
                <label for="biding">One-Way y Two-Way data binding</label>
              </div>

              <div>
                <input v-model="competencias" type="checkbox" name="mvm" id="mvm" value="El patrón de diseño MVVM">
                <label for="mvm">El patrón de diseño MVVM</label>
              </div>
            </div>

            <div class="form-check">
              <div>
                <input v-model="competencias" id="directivas" type="checkbox" name="directivas" value="Directivas">
                <label for="directivas">Directivas</label>
              </div>

              <div>
                <input v-model="competencias" id="estado" type="checkbox"  name="estado"  value="Estado">
                <label for="estado">Estado</label>
              </div>
            </div>
        </div>
        <hr>

        <div class="form-field">
          <label for="opinion">Opinión</label>
          <textarea v-model="opinion" rows="2" cols="50" id="opinion" name="opinion" ></textarea>
        </div>
    </div>

      <div class="wrapper__display">
            <h1>{{ emoji }}</h1>

            <h1>{{ titulo }}</h1>

            <h3><strong>Y me parece: </strong></h3>
              <p><em>{{ apreciacion }}</em></p>
            
            <h3><strong>He aprendido:</strong></h3>

            <strong><em>{{ competencias }}</em></strong>
            <br>
            
            <strong>Mi opinión hasta ahora del framework es: </strong>

            <p><em>{{ opinion }}</em></p>
      </div>
  </div>
</template>



<script>
export default {
  name: "App",
  data() {
    return {
      titulo: "",
      emoji: "",
      apreciacion: "",
      competencias: [],
      opinion: "",
    };
  }
};
</script>


<style>

  .container {
  display: flex;
  margin: 40px;
  gap: 20px;
}


.form-wrapper {
  padding: 25px; 
  border-radius: 15px; 
  border: 1px solid gold;
  color: #ffffff;
  background-image: linear-gradient(to bottom right, #273542, #1b2733 , #06101a);
  box-shadow: 0 5px 10px black;
  display: flex;
  flex-direction: column;
  gap: 16px; 
}

.wrapper__display { 
  text-align: center;
  padding: 20px;
  color: indigo;
  border-radius: 16px; 
  border: 1px solid #90baca;
  width: 60%;
  background-image: linear-gradient(to top left, #c0b4c0, #f0e3f0, #c0b4c0, #f0e3f0,#c0b4c0, #9482a1, #8383cf);
  box-shadow: 0 5px 15px black;
}

.form-field {
  display: flex;
  align-items: center;
  gap: 10px; 
}

.form--competencias {
  display: flex;
  align-items: start;
  gap: 15px; 
  margin-left: 5px;
}

select,
input {
  padding: 5px; 
}

.form-check {
  display: flex;
  flex-direction: column;
  align-items: start;
  gap: 10px; 
}

.form-checkbox div {
  display: flex;
  gap: 8px; 
  align-items: start;
  text-align: start;
}

hr {
  width: 100%;
  height: 0;
  border: none;
  border-top: 1px solid gold;
}

</style>
