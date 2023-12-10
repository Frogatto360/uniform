<template>
    <div id="app" class="form-container">

      <div class="FormularioAvaliativo">

        <h2> FORMULÁRIO </h2>

        <div class="form-group">
          <label for="name">Nome completo:</label> 
          <input type="text" id="name" placeholder="Insira seu Nome aqui" v-model="name" :class="{ 'is-invalid': !nameValid }"/> 
        </div>

        <div class="form-group">
          <label for="email">Endereço de e-mail:</label> 
          <input type="email" id="email" placeholder="Insira seu Email aqui" v-model="email" :class="{ 'is-invalid': !emailValid }"/> 
        </div>

        <div class="form-group">
          <label for="age">Idade:</label> 
          <input type="number" id="age" placeholder="insira sua Idade aqui" v-model="age" :class="{ 'is-invalid': !ageValid }"/> 
        </div>

        <div class="form-group">
          <label for="description">Uma Breve Descrição de si mesmo:</label> 
          <textarea id="description" placeholder="Insira sua Descrição aqui" v-model="description" :class="{ 'is-invalid': !descriptionValid }"></textarea>
        </div>

        <div class="form-buttons">
          <button type="button" @click="validateAndSubmitForm" :disabled="formSubmitted" class="btn btn-primary"> {{ formSubmitted ? 'Enviado' : 'Enviar' }}
          </button>
          <button type="button" @click="clearForm" class="btn btn-secondary"> Limpar </button>
        </div>

      </div>
  
      <div class="submitted-data" v-if="formSubmitted">
        <h3> Dados do formulário </h3>
        <ul>
          <strong>Nome:</strong> {{ submittedData.name }} <br>
          <strong>E-mail:</strong> {{ submittedData.email }} <br>
          <strong>Idade:</strong> {{ submittedData.age }} <br>
          <strong>Descrição:</strong> {{ submittedData.description }} <br>
        </ul>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        name: "",
        email: "",
        age: null,
        description: "",
        nameValid: true,
        emailValid: true,
        ageValid: true,
        descriptionValid: true,
        formSubmitted: false,
        submittedData: {
          name: "",
          email: "",
          age: null,
          description: "",
        },
      };
    },
    methods: {
      validateAndSubmitForm() {
        this.nameValid = !!this.name;
        this.emailValid = /^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(this.email); 
        this.ageValid = !isNaN(this.age) && this.age > 0;
        this.descriptionValid = !!this.description;
  
        if (this.nameValid && this.emailValid && this.ageValid && this.descriptionValid) {
          this.submitForm();
        } else {
          alert("Por favor, preencha todos os campos corretamente.");
        }
      },
      submitForm() {
        const userData = {
          name: this.name,
          email: this.email,
          age: this.age,
          description: this.description,
        };
        this.submittedData = userData;
        this.formSubmitted = true;
      },
      clearForm() {
        this.name = "";
        this.email = "";
        this.age = null;
        this.description = "";
        this.nameValid = true;
        this.emailValid = true;
        this.ageValid = true;
        this.descriptionValid = true;
        this.formSubmitted = false;
        this.submittedData = {
          name: "",
          email: "",
          age: null,
          description: "",
        };
      },
    },
  };
  </script>
  
  <style scoped>
  .FormularioAvaliativo {
    width: 700px;
  }

  h2 {
    color: #E54A59;
  }
  
  h3 {
    color: #E54A59;
  }
  .form-container {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items:center;
    height: 100vh;
    background-color: #ebebeb;
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  }
  
  .form {
    max-width: 400px;
    width: 100%;
    padding: 40px;
    background-color: #ffffff;
    border-radius: 16px;
    box-shadow: 0 0 10px #E54A59;
  }
  
  .form-group {
    margin-bottom: 20px;
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: space-between;
  }
  
  label {
    font-family:'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    margin-bottom: 8px;
  }
  
  input {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    width: 400px;
    height: 25px;
    border-color: #2b2b2b;
    border-radius: 4px;
  }
  
  textarea {
    resize: both; 
    overflow: auto;
    width: 400px; 
    min-height: 50px;
    min-width: 200px; 
    max-width: 100%; 
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    border-radius: 4px;
    border-color:#2b2b2b;
  }
  
  .form-control {
    width: 100%;
    padding: 10px;
    font-size: 14px;
    border: 1px solid #ddd;
    border-radius: 4px;
    box-sizing: border-box;
    position: center;
  }
  
  button {
    width: 48%;
    padding: 12px;
    font-size: 16px;
    margin-right: 4%;
    margin-bottom: 10px;
    cursor: pointer;
    position: center;
    border-radius: 4px;
    background-color: #E54A59;
    border-block-color: #2b2b2b;
  }
  
  .form-buttons {
    display: flex;
    justify-content: space-between;
  }
  
  strong{
    color:#E54A59;
  }
  .submitted-data {
    margin-top: 10px;
    text-align: left;
    padding: 20px;
    border: 1px solid #E54A59;
    border-radius: 8px;
    width: auto;
    box-shadow:#e54a59;
  
  }
  
  .is-invalid {
    border: 1px solid red;
  }
  </style>