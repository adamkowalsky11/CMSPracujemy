<template>
<div>
  <v-card
    :loading="loading"
    class="mx-auto my-12"
    v-for="job in allJobs" :key="job.id"
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
      :src="job.logo.url"
    ></v-img>
    </v-col>
    <v-col>
      <v-row>
        <v-card-title>
          {{job.title}}
        </v-card-title>
        <v-card-text>
          {{job.company}}
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
        <v-chip disabled>{{job.salary}}</v-chip>

        <v-chip disabled>{{job.level}}</v-chip>
      </v-chip-group>
    </v-card-text>
  </v-row>
    </v-col>
</v-row>
  </v-card>
  </div>
</template>

<script>
  import gql from "graphql-tag"
  export default {
    data: () => ({
      loading: false,
      selection: 1,
     
    }),
     apollo: {
    allJobs: gql`{
      allJobs {
    id
    level
    salary
    title
    company
    logo {
      url
    }
  }
    }`,
  },

    methods: {
      reserve () {
        this.loading = true

        setTimeout(() => (this.loading = false), 2000)
      },
    },
  }
</script>