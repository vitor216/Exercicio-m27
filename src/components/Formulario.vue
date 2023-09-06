<script setup>
const props = defineProps(['operacao', 'num1', 'num2', 'botao', 'calcular'])
</script>

<template>
    <form @button.prevent="props.calcular">
            <div class="row">
                <div class="col">
                    <input @keyup=" props.num1" type="number" required placeholder="Primeiro Valor" class="form-control">
                    <input @keyup=" props.num2" type="number" required placeholder="Segundo Valor" class="form-control">
                </div>
                    <div class="col-md-2">
                    <label>Selecione a operação:</label>
                    <select @change= "props.operacao" class="form-control">
                    <option value="Adicao" >Adição</option>
                    <option value="Subtracao">Subtração</option>
                    <option value="Multiplicacao">Multiplicação</option>
                    <option value="Divisao">Divisão</option>
                    </select>
                </div>
                    <div class="col-md-2">
                    <Button :disabled="props.botao" type="button" class="btn btn-success" @click="props.calcular">Calcular</Button>
                    </div>
            </div>
        </form>
</template>

<style scoped>
select{
    border-color: rgb(10, 186, 218);
}
input{
    border-color: rgb(10, 186, 218);
    margin-bottom: 5px;
}
</style>