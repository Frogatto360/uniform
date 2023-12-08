<template>
 <form action="">
    <div class="__form-div">
        <label for="nome"> <strong> Nome completo </strong> </label>
        <input type="text" id="nome" placeholder="Insira seu nome completo aqui" required>
    </div>

    <div class="__form-div">
        <label for="email"> <strong> Endereço de Email </strong> </label>
        <input type="email" id="email" placeholder="Insira seu email aqui" required>
    </div>
    
    <div class="__form-div">
        <label for="idade"> <strong> Idade </strong> </label>
        <input type="number" id="idade" placeholder="Insira sua idade aqui" required>
    </div>

    <div class="__form-div">
        <label for="descricao"> <strong> Uma Breve Descrição de Si Mesmo </strong> </label>
        <textarea name="" id="descricao" cols="30" rows="10" required> </textarea>
    </div>

    <button type="submit"> Enviar </button>
 </form>
</template>

<script>
    export default {
        name: 'FormularioAvaliativo'
    }
</script>

<style>
    form{
        background-color: white;
        border-radius: 2px;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        width: 500px;
        height: 500px;
    }

    label{
        width: 100%;
    }

    input{
        width: 100%;
        border: 1px solid #ccc;
        border-radius: 2px;
    }

    .__form-div{
        width: 80%;
        display: flex;
        flex-direction: column;
        margin-top: 25px;
    }

    button{
        margin-top: 50px;
        width: 25%;
        height: 25px;
        text-align: center;
        border-radius: 2px;
        border: 1px solid #ccc;
        font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    }
</style>