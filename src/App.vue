<script setup>
import Cabecalho from './components/Cabecalho.vue'
import Formulario from './components/Formulario.vue'
import Resultado from './components/Resultado.vue'

function calcular() {
    let tn1 = document.getElementById('txtn1');
    let tn2 = document.getElementById('txtn2');

    let operacao = document.getElementById('operacao');
    let resultado = document.getElementById('resultado');

    let n1 = parseFloat(tn1.value);
    let n2 = parseFloat(tn2.value);
    let operador = operacao.value;

    if (operador == 'adicao') {
        let s = n1 + n2;
    }
    if (operador == 'subtracao') {
        let s = n1 - n2;
    }
    if (operador == 'multiplicacao') {
        let s = n1 * n2;
    }
    if (operador == 'divisao') {
        let s = n1 / n2;
    }
    if (operador ==''){
        return resultado.innerHTML = 'Necessario escolher operação!';
    }
    
    resultado.innerHTML = `A ${operador} entre ${n1} e ${n2} é igual a ${s}`
}

const botaoEstaDesabilitado = true;

const EnderecoDaImagemDaCalculadora = "https://media.istockphoto.com/id/544462430/pt/vetorial/calculadora-isolada-numa-cor-de-fundo.jpg?s=612x612&w=0&k=20&c=W9AdCLbbUWCH6zm-SFrLJRLswRrtR9msfUHREFhOZR8="

</script>

<template>
    <div class="container">
        <Cabecalho :enderecoda-imagem="EnderecoDaImagemDaCalculadora" />
        <Formulario :botao-esta-desabilitado="botaoEstaDesabilitado"/>
        <Resultado/>
    </div>    
</template>

<style scoped>
header {
    background-color: rgb(10, 186, 218);
}
</style>