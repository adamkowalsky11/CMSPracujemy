<template>
  
  
  <v-row justify="center" align="center">
    
    <v-col cols="2" sm="8" md="6">
      <h1 justify="center" align="center" class="my-15"> Znajdź swoją wymarzoną pracę </h1>
      
      
  <v-carousel v-model="model">
    <v-carousel-item
    
      v-for="(color) in colors"
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
        <!--<div class="image"> <v-img max-height="128" max-width="250" src="https://www.datocms-assets.com/59409/1638966135-pjatk.jpeg"></v-img></div>-->
          <div class="text-h2">
            <!-- Comment SLAJD {{ i + 1 }}-->
            Pracujemy.pl
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
  data: () => ({
      model: 0,
      colors: [
        'primary',
        'secondary',
        'yellow darken-2',
        'red',
        'orange',
      ],
    }),


    
  setup() {
    
  },
  
})
</script>
