<script setup>
    const props = defineProps(['botaoEstaDesabilitado'])
</script>
<template>
    <form id="Form-Calculadora">
        <div class="row">
            <div class="col">
                <input type="number" id="txtn1" required placeholder="Primeiro Valor" class="form-control">
                <input type="number" id="txtn2" required placeholder="Segundo Valor" class="form-control">
            </div>
            <div class="col-md-2">
                <label for="operacao">Selecione a operação:</label>
                <select name="operacao" id="operacao" @change="calcular()">
                    <option value=""></option>
                    <option value="adicao">Adição</option>
                    <option value="subtracao">Subtração</option>
                    <option value="multiplicacao">Multiplicação</option>
                    <option value="divisao">Divisão</option>
                </select>
            </div>
            <div class="col-md-2">
                <Button :disabled="botaoEstaDesabilitado" type="button" class="btn btn-success"
                    @click="calcular()">calcular</Button>
            </div>
        </div>
    </form><br />
</template>