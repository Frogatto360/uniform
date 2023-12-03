<template>
  <FormularioAvaliativo/>
</template>

<script>
  import FormularioAvaliativo from './components/form.vue'

  export default{
    name: 'App',

    components: {
      FormularioAvaliativo
    }
  }

</script>

<style>
  *{
    padding: 0;
    margin: 0;
    box-sizing: border-box;
  }

  body{
    height: 100vh;
    width: 100%;
    background-color: #ebebeb;
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    display: flex;
    align-items: center;
    justify-content: center;
  }
</style>
