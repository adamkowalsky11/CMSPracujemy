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
    
    <v-btn
      :disabled="!valid"
      color="success"
      class="mr-4"
      @click="validate"
    >
      Validate
    </v-btn>

    <v-btn
      color="error"
      class="mr-4"
      @click="reset"
    >
      Reset Form
    </v-btn>

    <v-btn
      color="warning"
      @click="resetValidation"
    >
      Reset Validation
    </v-btn>
  </v-form>
  </v-card>
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
