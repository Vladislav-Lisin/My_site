<template>
  <div class="wrapper">
    <h1> Приложение погода </h1>
    <p> Узнать погоду в городе {{ city == "" ? "" : cityName }}</p>
    <input type="text" v-model="city" placeholder="Введите город">
    <button v-if=" city != ''" v-on:click="getWeather(this)"> Получить погоду</button>
    <button disabled v-else> Введите город </button>
    <p class="error"> {{ error }}</p>
  </div>

</template>

<script>
export default {
  data(){
    return{
      city: '',
      error: ''
    }
  },
  computed:{
    cityName(){
      return '"'+ this.city +'"'
    }
  },  
  methods: {
    getWeather(){
      if(this.city.trim().length <2){
        this.error = "Нужно название более одного символа";
        return false
      }
      this.error = "";
      
    }
  }
  
}
</script>



<style scoped>
.error{
  margin-top: 20px;
  color: #a82424;
  font-size: 18px;
}

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