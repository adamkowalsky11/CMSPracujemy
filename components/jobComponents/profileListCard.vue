<template>
<div>
  <v-header>lista pracodawców</v-header>
  <v-card
    :loading="loading"
    class="mx-auto my-12"
  >
  <v-row>
    <v-col cols="2">
      <v-img
      max-height="150"
      max-width="150"
      src="https://cdn.vuetifyjs.com/images/cards/cooking.png"
    ></v-img>
    </v-col>
    <v-col cols="1">
      <v-divider vertical></v-divider>
    </v-col>
    <v-col>
      <v-card-text>
        nazwa firmy...
      </v-card-text>

    </v-col>
     <v-col cols="1">
      <v-divider vertical></v-divider>
    </v-col>
    <v-col cols="3">
      <v-card-header>
        dane kontaktowe
      </v-card-header>
      <v-card-text>
      1500zł/h 
      </v-card-text>
    </v-col>
  </v-row>
  
  </v-card>
  </div>
</template>

<script>
  export default {
    data: () => ({
      loading: false,
      selection: 1,
    }),

    methods: {
      reserve () {
        this.loading = true

        setTimeout(() => (this.loading = false), 2000)
      },
    },
  }
</script>