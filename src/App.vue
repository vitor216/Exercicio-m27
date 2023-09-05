<script setup>
import { reactive } from 'vue';

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
        <header class="p-5 mb-4 mt-4 rounded-3">
            <div id="cabecalho">
                <h1>Minha Calculadora</h1>
                <img :src="EnderecoDaImagemDaCalculadora" alt="">
            </div>
            <p>
                Escolha a Operação e Bons Calculos...
            </p>
        </header>
        <form @button.prevent="Calcular()">
            <div class="row">
                <div class="col">
                    <input @keyup="evento => estado.num1 = evento.target.value" type="number" required placeholder="Primeiro Valor" class="form-control">
                    <input @keyup="evento => estado.num2 = evento.target.value" type="number" required placeholder="Segundo Valor" class="form-control">
                    <input @keyup="evento => estado.Nome = evento.target.value" type="text" required placeholder="Digite seu Nome" class="form-control">
                </div>
                    <div class="col-md-2">
                    <label>Selecione a operação:</label>
                    <select @change="evento => estado.Operation = evento.target.value" class="form-control">
                    <option value="Adicao" >Adição</option>
                    <option value="Subtracao">Subtração</option>
                    <option value="Multiplicacao">Multiplicação</option>
                    <option value="Divisao">Divisão</option>
                    </select>
                </div>
                    <div class="col-md-2">
                    <Button :disabled="botaoEstaDesabilitado" type="button" class="btn btn-success" @click="Calcular()">Calcular</Button>
                    </div>
            </div>
        </form>
        <div class="col-bg-2">
            <div class="form-control">
                <span v-if="estado.num1 && estado.num2 != ''" ><h2>Resultado: {{ Calcular() }}</h2></span>
                <span v-else-if="estado.num1 || estado.num2 ==='' "><h2>Digite os dois números</h2></span>
            </div>
        </div>

        
    </div>
</template>

<style scoped>
header {
    background-color: rgb(10, 186, 218);
}
img {
    max-width: 75px;
}

input, select{
    border-color: rgb(10, 186, 218);
}

#cabecalho {
display: flex;
align-items: center;
justify-content: space-between;
}
#resultado {
    border-color: rgb(10, 186, 218);
}
</style>