<template>
    
    
    <div>
        Cadastrar um entregador:
        <v-sheet class="mx-auto" width="300">
        <v-form ref="form">
        <v-text-field
          v-model="name"
          :counter="10"
          :rules="nameRules"
          label="Nome do motorista"
          required
        ></v-text-field>

        <v-text-field>
          label="CPF"
          required
        ></v-text-field>

        <v-text-field
          label="Endereço"
          required
        ></v-text-field>

        <v-text-field
          label="Telefone"
          required
        ></v-text-field>
  
        <div class="d-flex flex-column">
          <v-btn
            class="mt-4"
            color="success"
            block
            @click="validate"
          >
            Enviar
          </v-btn>

        </div>
      </v-form>
    </v-sheet>
    </div>
    
  </template>

<script>
  export default {
    data: () => ({
      name: '',
      nameRules: [
        v => !!v || '*Obrigatório',
        v => (v && v.length <= 10) || 'O ID é menor do que 10 caracteres',
      ],
      
      select: null,
      items: [
        'Item 1',
        'Item 2',
        'Item 3',
        'Item 4',
      ],
      
    }),

    methods: {
      async validate () {
        const { valid } = await this.$refs.form.validate()

        if (valid) alert('Form is valid')
      },
      
    },
  }
</script>

<style>

</style>