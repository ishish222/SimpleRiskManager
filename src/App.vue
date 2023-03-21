<script>
    import { Authenticator } from '@aws-amplify/ui-vue'
    import { Amplify } from 'aws-amplify'
    import awsconfig from './aws-exports'
    import '@aws-amplify/ui-vue/styles.css'

    Amplify.configure(awsconfig)

    export default {
        components: {
            Authenticator
        },
    }

</script>

<template>
  <authenticator :social-providers="['google']">
    <template v-slot="{ user, signOut }">
        <center>
      <h1>Helloo {{ user.username }}!</h1>
        <br>
        <br>
        <br>
        This is accessible after login
        <br>
      <button @click="signOut">Sign Out</button>
        </center>
    </template>
  </authenticator>
This is accessible without a login
</template>
