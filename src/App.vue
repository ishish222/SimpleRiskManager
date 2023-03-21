<script>
    import { Authenticator } from '@aws-amplify/ui-vue'
    import { Amplify } from 'aws-amplify'
    import awsconfig from './aws-exports'

    Amplify.configure(awsconfig)


    export default {
        components: {
            Authenticator
        },
    }

</script>

<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <authenticator :social-providers="['google']">
    <template v-slot="{ user, signOut }">
      <h1>Helloo {{ user.username }}!</h1>
      <button @click="signOut">Sign Out</button>
    </template>
  </authenticator>

</template>
