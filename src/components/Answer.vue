// Componente da Resposta
<template>
    <div class="alert alert-success text-center">
        <h1>Está sabendo da empresa hein!</h1>
        <hr>
        <button class="btn btn-primary" @click="onNextQuestion">Bora lá, sei muito mais</button>
    </div>
</template>


<style>
    .alert {
        box-shadow: 5px 5px rgba(0, 0, 0, 0.3);
    }

</style>


<script>

    export default{
        methods: {
            onNextQuestion() {
                this.$emit('confirmed');
            }
        }
    }
</script>
