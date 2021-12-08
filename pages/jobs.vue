<template>
<<<<<<< HEAD
  <v-row>
    <v-col class="text-center">
      <img
        src="/v.png"
        alt="Vuetify.js"
        class="mb-5"
      >
      <blockquote class="blockquote">
        &#8220;First, solve the problem. Then, write the code.&#8221;
        <footer>
          <small>
            <em>&mdash;John Johnsonff</em>
          </small>
        </footer>
      </blockquote>
=======
  <v-row justify="right" align="center">
    <v-col cols="12" sm="8" md="6">
      <div>
        <h2>
          <li v-for="(job, index) in allJobs" :key="index">
            <nuxt-link :to="`/blog/${job.slug}`">{{job.title}}</nuxt-link>
          </li>
        </h2>
      </div>
>>>>>>> master
    </v-col>
  </v-row>
</template>

<script>
import gql from 'graphql-tag'
import { defineComponent } from '@vue/composition-api'

export default defineComponent({
  apollo:{
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
        jsontest
        slug
      }
    }`,
  },
  setup() {
    
  },
})
</script>
