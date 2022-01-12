<template>
  <v-card
    :loading="loading"
    class="mx-auto my-12"
  >
  <v-row >
    <v-col cols="3">
    <template slot="progress">
      <v-progress-linear
        color="deep-purple"
        height="10"
        indeterminate
      ></v-progress-linear>
    </template>

    <v-img
      max-height="200"
      max-width="200"
      src="https://cdn.vuetifyjs.com/images/cards/cooking.png"
    ></v-img>
    </v-col>
    <v-col>
      <v-row>
        <v-card-title>
          Nazwa posady
        </v-card-title>
        <v-card-text>
          Nazwa firmy
        </v-card-text>
  <v-divider class="mx-4"></v-divider>
    
    </v-row>

   <v-row>
  
  <v-card-text>
      <v-chip-group
        v-model="selection"
        active-class="deep-purple accent-4 white--text"
        column
      >
        <v-chip disabled>Stawka</v-chip>

        <v-chip disabled>Poziom</v-chip>
      </v-chip-group>
    </v-card-text>
  </v-row>
    </v-col>
</v-row>
  </v-card>
</template>

<script>
const zmienna = [,]
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