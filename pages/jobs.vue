
<template>
<div>
  <header>
    Oferty pracy
  </header>
  <v-row>
    <v-col cols="4">
  <search-parameter/>
  </v-col>
  <v-col>
  <price-range/>
  </v-col>
  
  </v-row>
    <location/>

  <card/>
</div>
</template>

<script>
import gql from 'graphql-tag'
import { defineComponent } from '@vue/composition-api'
import priceRange from '~/components/jobComponents/priceRange.vue'
import SearchParameter from '~/components/jobComponents/searchParameter.vue'
import Card from '~/components/jobComponents/card.vue'
import location from '~/components/jobComponents/location.vue'


export default defineComponent({
  components: { priceRange, SearchParameter, Card, location },
  
    Cardapollo:{
    allJobs: gql`{
      allJobs {
        id
        logo{
          url
        }
        level
        company
        description
        title
        salary
        slug
      }
    }`,
  },
  setup() {
    
  },
})
</script>