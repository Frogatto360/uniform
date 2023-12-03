<template>
 <form action="">
    <div class="__form-div">
        <label for=""> <strong> Nome completo </strong> </label>
        <input type="text" required>
    </div>

    <div class="__form-div">
        <label for=""> <strong> Endereço de Email </strong> </label>
        <input type="email" required>
    </div>
    
    <div class="__form-div">
        <label for=""> <strong> Idade </strong> </label>
        <input type="number" required>
    </div>

    <div class="__form-div">
        <label for=""> <strong> Uma Breve Descrição de Si Mesmo </strong> </label>
        <textarea name="" id="" cols="30" rows="10" required> </textarea>
    </div>

    <button> Enviar </button>
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
    }
</style>