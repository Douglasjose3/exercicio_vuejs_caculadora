<script setup>
import { reactive } from 'vue';
import Cabecalho from './components/Cabecalho.vue';
import Operation from './components/Operation.vue';
import Results from './components/Results.vue';

  const estado = reactive ({
    operadores: 'somar',
    numero1: '',
    numero2: ''
  })

  const resultado = () => {
    const {operadores} = estado
    switch(operadores) {
      case 'subtrair':
        return parseFloat(estado.numero1) - parseFloat(estado.numero2);
      case 'multiplicar':
        return parseFloat(estado.numero1) * parseFloat(estado.numero2);
      case 'dividir':
        return parseFloat(estado.numero1) / parseFloat(estado.numero2);
      
      default: 
      return parseFloat(estado.numero1) + parseFloat(estado.numero2);
    }
  }

</script>


<template>
  <header>
    <div class="container">
      <Cabecalho />
      <Operation :operacao="evento => estado.operadores = evento.target.value" :numero1="evento => estado.numero1 = evento.target.value" :numero2="evento => estado.numero2 = evento.target.value"></Operation>
      <Results :numero1="estado.numero1" :numero2="estado.numero2" :result="resultado()" />
    </div>
  </header>
</template>


<!--
<template>
  <div class="container">
    <header class="p-5 pb-1 mt-5 mb-4 bg-primary bg-gradient text-light text-center rounded-5">
      <h1>Calculadora</h1>
    </header>
  </div>

  <div class="container">
    <form class="operation">
      <div class="row bg-secondary bg-gradient p-5 rounded-5">
        <div class="col-md-4">
          <input @keyup="props.numero1" class="form-control" type="number" placeholder="Digite o primeiro valor" required>
        </div>

        <div class="col-md-4">
          <select @change="props.operation" class="form-select input-group">
            <option>Escolha a Função Aritmética</option>
            <option value="somar">Somar</option>
            <option value="subtrair">Subtrair</option>
            <option value="multiplicar">Multiplicar</option>
            <option value="dividir">Dividir</option>
          </select>
        </div>

        <div class="col-md-4">
          <input @keyup="props.numero2" class="form-control" type="number" placeholder="Digite o segundo valor" required>
        </div>
      </div>
    </form>
  </div>

  <div class="result">
    <footer class="pt-5 pb-1 mt-4 mb-3 bg-info bg-gradient text-center rounded-5">
      <h3>O resultado é:</h3>
      <h1 v-if="props.numero1 && props.numero2 !=''">{{ props.result }}</h1>
      <span v-else-if="props.numero1 || props.numero2 === ''">Você precisa digitar os números</span>
    </footer>
  </div> 

</template>
-->



<style scoped>
/*
h1 {
  margin-bottom: 50px;
}
h6 {
  color: aliceblue;
}
*/
</style>./components/Cabecalho.vue
