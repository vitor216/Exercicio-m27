<script setup>
const props = defineProps(['num1', 'num2', 'resultado'])
</script>

<template>
    <div class="col-bg-2">
            <div class="form-control" id="resultado">
                <span v-if="props.num1 && props.num2 != ''" ><h2>Resultado: {{ props.resultado }}</h2></span>
                <span v-else-if="props.num1 || props.num2 ==='' "><h3>Digite os dois números</h3></span>
            </div>
        </div>
</template>

<style scoped>
#resultado {
    border-color: rgb(10, 186, 218);
    background-color: rgb(10, 186, 218);
}
</style>