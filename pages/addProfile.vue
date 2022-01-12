<template>
<div>
    <div>
        <v-header >
            <v-title>stwórz profil</v-title>
        </v-header>

        <v-card>
        <v-form
    ref="form"
    v-model="valid"
    lazy-validation
  >
    <v-text-field
      v-model="name"

      label="Nazwa Firmy"
      required
    ></v-text-field>

    <v-text-field
      v-model="email"
      :rules="emailRules"
      label="E-mail"
      required
    ></v-text-field>
    
    <v-text-field 
    v-model="phoneNumber"
    label="Numer telefonu">
        
    </v-text-field>
    <v-textarea 
        auto-grow
        label="Opis"
    ></v-textarea>

    <v-file-input
    accept="image/*"
    label="Logo"
  ></v-file-input>
    
    

   

  </v-form>
  </v-card>
  <v-btn
    block
      :disabled="!valid"
      color="success"
      class="mr-4"
      @click="validate"
    >
      Zatwierdź
    </v-btn>
    </div>
</div>
    
</template>
<script>
import { defineComponent } from '@vue/composition-api'

export default defineComponent({
    setup() {
        
    },
})
</script>
