<template>
    <div>
        <h1 v-if="post">{{post.title}}</h1>
        <p v-if="post">{{post.content}}</p>
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
        }
    },

    setup() {
        
    },
})
</script>
