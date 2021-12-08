<template>
    <div>
        <h1 v-if="post">{{post.title}}</h1>
        <p v-if="post">{{post.content}}</p>
        <h1 v-if="job">{{job.title}}</h1>
        <v-img v-if="job" max-height="128" max-width="250" src="https://www.datocms-assets.com/59409/1638966135-pjatk.jpeg"></v-img>
        <p v-if="job">{{job.description}}</p>
        <p v-if="job">{{job.jsontest}}</p>
    </div>
</template>

<script>
import gql from 'graphql-tag'
import { defineComponent } from '@vue/composition-api'

export default defineComponent({
    apollo:{
        post:{
            query: gql`query Post($slug: String!){
                post(filter: { slug: {
                    matches: { pattern: $slug}
                }}){
                    title
                    content
                }
            }`,
            prefetch({route}){
                return{
                    slug: route.params.slug
                }
            },
            variables(){
                return{
                    slug: this.$route.params.slug
                }
            }
        },
        job:{
            query: gql`query Job($slug: String!){
                job(filter: { slug: {
                    matches: { pattern: $slug}
                }}){
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
                }
            }`,
            prefetch({route}){
                return{
                    slug: route.params.slug
                }
            },
            variables(){
                return{
                    slug: this.$route.params.slug
                }
            }
        }
    },

    setup() {
        
    },
})
</script>
