<template>
  <div class="wrapper">
    <h1> Приложение погода </h1>
    <p> Узнать погоду в городе {{ city == "" ? "Тверь" : city }}</p>
    <input type="text" v-model="city" placeholder="Введите город">
    <button v-if=" city != ''"> Получить погоду</button>
    <button disabled v-else> Введите город </button>
  </div>

</template>

<script>
export default {
  data(){
    return{
      city: '',
    }
  }
  
}
</script>



<style scoped>
.wrapper {
  width: 900px;
  height: 500px;
  border-radius: 50px;
  padding: 20px;
  background: #1f0f24;
  text-align: center;
  color: #fff;
}

.wrapper h1 {
  margin-top: 50px;
}

.wrapper p {
  margin-top: 20px;
  font-size: 20px;
}

.wrapper input {
  margin-top: 30px;
  background: transparent;
  border: 0;
  border-bottom: 2px solid #110813;
  color: #fcfcfc;
  font-size: 14px;
  padding: 5px 8px;
  outline: none;
}

.wrapper button:disabled {
  background: #532653;
  cursor: not-allowed;
  color: #cecccc;
  
}

.wrapper button {
  margin-top: 30px;
  background: #6e2d6e;
  border: 0;
  color: #fff;
  font-size: 14px;
  padding: 5px 8px;
  border-radius: 5px;
  cursor: pointer; 
  transition: transform 500ms ease;
}

.wrapper button:hover {
  transform: scale(1.1) translateY(-5px);
}

.wrapper input:focus{
  border-bottom-color: #6e2d6e;
}


</style>