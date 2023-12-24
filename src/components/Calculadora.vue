<script>
import { parse } from 'vue/compiler-sfc';

    export default{
        name:'Calculadora',
        data(){
            return{
               input1 : 0,
               input2 : 0,
               resultado : 0

            };
        },
        methods:{
            somar(){
                this.resultado = parseFloat(this.input1) + parseFloat(this.input2);
            },
            subtrair(){
                this.resultado = parseFloat(this.input1) - parseFloat(this.input2);
            },
            dividir(){
                if (parseFloat(this.input2) !== 0) {
                    this.resultado = parseFloat(this.input1) / parseFloat(this.input2);
                } else {
                    this.resultado = "Não é possível dividir por zero";
                }
            },
            multiplicar(){
                this.resultado = parseFloat(this.input1) * parseFloat(this.input2);
            },
        }

        }
</script>
<template>
    <div class="calculadora">
        <div class="resultado">
            <h5>Digite aqui os numeros para saber o resultado:</h5>
            <p class="resultado">{{resultado}}</p>
        </div>
      <div class="inputs">
        <input v-model="input1" class="n1" type="number"  required>
        <input v-model="input2" class="n1" type="number"  required>
      </div>
      <div class="btns">
        <button @click="somar" class="btn" type="button">+</button>
        <button @click="subtrair" class="btn" type="button">-</button>
        <button @click="dividir" class="btn" type="button">/</button>
        <button @click="multiplicar" class="btn" type="button">*</button>
    </div>
</div>
</template>
<style scoped>
    .resultado{
      text-align: center;
      margin-bottom: 10px;
      margin-top: 10px;
      color: rgb(0, 255, 20);
      font-weight: bold;
      font-size: 25px;
      position: relative;
    }
    .calculadora{
        width:100%;
        max-width: 600px;
        margin: 0 auto;
        margin-top: 200px;
        height: 300px;
        border-radius: 10px;
        display: flex;
        flex-direction: column;
        align-items: center;
        background-image: url(/public/img/plano-de-contas.jpg);
        background-repeat: no-repeat;
        background-size: cover;
        background-position: bottom;
        box-shadow: 10px 10px 10px white;
        position: relative;
        
    }
        .calculadora:before {
        content: "";
        width: 100%;
        height: 100%;
        opacity: .4;
        border-radius: 10px;
        background-color: #000;
        position: absolute;
        top: 0;
        left: 0;
    }
    
    .inputs  {
       display: flex;
       flex-direction: row;
       position: relative;
    }
    
    .n1{
        max-width: 50px;
        height: 50px;
        margin: 5px;
        text-align: center;
        border: 1px solid rgb(83, 255, 120);; 
        border-radius: 20%;
    }
    .n1:focus{
        outline: none;
    }
    .btns{
        position: relative;
    }
    .btn{
        padding: 5px;
        margin: 20px;
        font-size: 20px;  
        width: 40px;
        border-radius: 30%;
        border: 1px solid rgb(83, 255, 120);
        color: rgb(255, 255, 255);
        background-image: linear-gradient(rgb(0, 255, 21),rgb(0, 195, 255)); 
        transition: 0.7s;
    }
    .btn:hover{
        background-image: linear-gradient(rgb(0, 195, 255),rgb(0, 255, 21)); 
        border: 1px solid rgb(0, 195, 255);
        color: rgb(0, 60, 78);
        box-shadow: 2px 2px 2px white;
        transform: scale(1.2);
     }
     .calcular{
         position: relative;
         width: 150px;
         padding: 5px;
         font-size: 20px;  
         border-radius: 50%;
         border: 1px solid rgb(83, 255, 120); 
         color: rgb(255, 255, 255);
         background-image: linear-gradient(rgb(0, 255, 21),rgb(0, 195, 255)); 
         transition: 0.8s;
     }
     .calcular:hover{
        background-image: linear-gradient(rgb(0, 195, 255),rgb(0, 255, 21)); 
        border: 1px solid rgb(0, 195, 255);
        color: rgb(0, 60, 78);
        box-shadow: 2px 2px 2px white;
        transform: scale(1.2);
     }
</style>