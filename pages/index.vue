<template>
  <v-row justify="right" align="center">
    <v-col cols="12" sm="8" md="6">
  <v-carousel v-model="model">
    <v-carousel-item
      v-for="(color, i) in colors"
      :key="color"
    >
      <v-sheet
        :color="color"
        height="100%"
        tile
      >
        <v-row
          class="fill-height"
          align="center"
          justify="center"
        >
          <div class="text-h2">
            Slide {{ i + 1 }}
          </div>
        </v-row>
      </v-sheet>
    </v-carousel-item>
  </v-carousel>
    </v-col>
  </v-row>
</template>

<script>
import gql from 'graphql-tag'
import { defineComponent } from '@vue/composition-api'

export default defineComponent({
  apollo:{
    allPosts: gql`{
      allPosts{
        title
        content
        slug
      }
    }`,
  },
  setup() {
    
  },
})
</script>
