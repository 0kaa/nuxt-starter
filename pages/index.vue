<template>
  <v-container>
    <h1>Starter Project</h1>
    {{ $apolloData.data.post }}
  </v-container>
</template>

<script>
import gql from 'graphql-tag'
const post = gql`
              query{
                post(id:1){
                  id
                  title
                  body
                  user{
                    id
                    name
                  }
                }
              }
`
export default {
  name: 'PageHome',
  apollo: {
    post: {
      query: post,
      prefetch: true
    }
  }

}
</script>
