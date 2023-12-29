
<script setup>
import {reactive} from 'vue';

const nome = "Marcos"
const meuObj = {
  nome: "Marcos",
  filmeFavorito: "A Culpa"
}
const img="https://static.dc.com/2023-05/flash_hub_carCar_batman_4x3a.jpg"
const imgsuperman = "https://media.newyorker.com/photos/5909527c1c7a8e33fb38a864/master/pass/Man_of_Steel-580.jpeg";
const botaoDesabilidado = true



const gostadoBatman = false
const gostadoSuperMan = false


const estaAutorizado = false

// let contador = 0
const estado = reactive({
  n1: "",
  n2: "",
  operacao:"soma",
  string: "",
})

function isN2Empty() {
      return 
};

function  resultado(){
  const {n1, n2 } = estado;
  if((estado.n2 === '' ||  estado.n2 === null) || (estado.n1 === '' ||  estado.n1 === null)){
    estado.string = "";
    return "Insira os 2 numeros";
  }else{
    const {operacao} = estado;
  if(operacao == "soma"){
    estado.string = n1+"+"+n2+" =";
    return parseInt(n1)+parseInt(n2);
  }if(operacao =="subtracao"){
    estado.string = n1+"-"+n2+" =";
    return parseInt(n1)-parseInt(n2);
  }if(operacao =="multiplicacao"){
    estado.string = n1+"*"+n2+" =";
    return parseInt(n1)*parseInt(n2);
  }
  }
  }  
  




</script>

<template>


 

  <div class="container">
    


  </div>

  <div class="container-fluid d-flex align-items-center justify-content-center vh-100">
  <div class="container">
    <h1 class="text-center mb-4 mt-4">Calculadora Aritmetica</h1>
    


    <!--<input  :class="{ invalido: estado.transferindo > estado.saldo }" type="number" @keyup="evento => estado.transferindo = evento.target.value" placeholder="Quantia para transfeir" name="" id=""> Pode ser tambem validar --> 
    <div class="row">
        <div class="col-3"></div>
        <div class="col-2">
          <input  type="number"  class="form-control" @keyup="evento => estado.n1 = evento.target.value" placeholder="Valor 1" name="" id="">
        </div>
        <div class="col-2">
          <input  type="number" class="form-control" @keyup="evento => estado.n2 = evento.target.value" placeholder="Valor 2" name="" id="">
        </div>
        <div class="col-2">
          <select @change="evento => estado.operacao   = evento.target.value" class="form-control" name="" id="">
            <option value="soma" >Soma</option>
            <option value="subtracao">Subtracao</option>
            <option value="multiplicacao">Multiplicacao</option>
          </select>
         </div>
         <div class="col-3"></div>
     
    </div>
    <div class="row">
     <h4 class="text-center mt-4">
      {{ estado.string}}
       {{ resultado()}}
     </h4>
    </div>
  </div>
</div>

  
</template>

<style scoped>


</style>
