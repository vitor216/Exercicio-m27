<script setup>
import { reactive } from 'vue';
import Cabecalho from './components/Cabecalho.vue';
import Formulario from './components/Formulario.vue';
import Resultado from './components/Resultado.vue';

const estado = reactive({
    Operation: 'Adicao',
    num1: '',
    num2: '',
})

const Calcular = () => {
    const { Operation } = estado;
    switch (Operation) {
        case 'Subtracao':
            return parseFloat(estado.num1) - parseFloat(estado.num2);
        case 'Multiplicacao':
            return parseFloat(estado.num1) * parseFloat(estado.num2);
        case 'Divisao':
            return parseFloat(estado.num1) / parseFloat(estado.num2);
        default:
            return parseFloat(estado.num1) + parseFloat(estado.num2);
        }
}

const botaoEstaDesabilitado = true;
const EnderecoDaImagemDaCalculadora = "https://media.istockphoto.com/id/544462430/pt/vetorial/calculadora-isolada-numa-cor-de-fundo.jpg?s=612x612&w=0&k=20&c=W9AdCLbbUWCH6zm-SFrLJRLswRrtR9msfUHREFhOZR8="

</script>

<template>
    <div class="container">
    <Cabecalho :EnderecoDaImagem="EnderecoDaImagemDaCalculadora"/>
    <Formulario :operacao="evento => estado.Operation = evento.target.value" :num1="evento => estado.num1 = evento.target.value" :num2="evento => estado.num2 = evento.target.value" :botao="botaoEstaDesabilitado"/>
    <Resultado :num1="estado.num1" :num2="estado.num2" :resultado="Calcular()" />
    </div>
</template>

<style scoped></style>