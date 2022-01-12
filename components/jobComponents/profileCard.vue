<template>
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
        Dane kontaktowe
      </v-card-header>
      <v-card-text>
          <li>warszawa</li>
          <li>555343595</li>
      </v-card-text>
    </v-col>
  </v-row>
  <v-row>
    <v-col offset="1">
        <v-card-header>
            O firmie
        </v-card-header>
      <v-card-text>
Lorem ipsum dolor sit amet consectetur adipisicing elit. Ipsa, facere. Consequuntur, doloribus, adipisci veniam alias cumque dolorem hic numquam voluptas quo laudantium cum nostrum illo, accusamus nobis id placeat laborum!      </v-card-text>
        </v-col>
        
  </v-row>
  </v-card>
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