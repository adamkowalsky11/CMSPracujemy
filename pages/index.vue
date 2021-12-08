<template>
  <v-row justify="right" align="center">
    <v-col cols="12" sm="8" md="6">
      <div>
        <h2>
          <li v-for="(post, index) in allPosts" :key="index">
            <nuxt-link :to="`/blog/${post.slug}`">{{post.title}}</nuxt-link>
          </li>
        </h2>
      </div>
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
