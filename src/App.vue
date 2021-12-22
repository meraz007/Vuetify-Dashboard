<template>
  <v-app>
    <v-app-bar app color="primary" dark>
      <v-toolbar-title>Vuetify NavBar</v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn 
        text
        rounded>
        Home
      </v-btn>
      <v-btn 
      text 
      rounded
      >Login
      </v-btn>
    </v-app-bar>
    <!-- Log In page-->
    <v-content>
   <v-card width="400" class="mx-auto mt-5">
     <v-card-title>
       <h1 class="display-1">LogIn</h1>
     </v-card-title>
     <v-card-text>
       <v-form>
         <v-text-field label="Username" prepend-icon="mdi-account-circle" />
         <v-text-field label="Password" 
         :type="showPassword ? 'text' : 'password'"
         :append-icon="showPassword ? 'mdi-eye' : 'mdi-eye-off'"
         @click:append="showPassword = !showPassword"
         prepend-icon="mdi-lock" />
       </v-form>
     </v-card-text>
     <v-divider></v-divider>
     <v-card-actions>
       <v-btn color="success">Register</v-btn>
       <v-spacer></v-spacer>
       <v-btn class="info">Login</v-btn>
     </v-card-actions>
   </v-card>
   </v-content>
   <v-footer
    color="primary lighten-1"
    padless
  >
    <v-row
      justify="center"
      no-gutters
    >
      <v-btn
        v-for="link in links"
        :key="link"
        color="white"
        text
        rounded
        class="my-2"
      >
        {{ link }}
      </v-btn>
      <v-col
        class="primary lighten-1 py-4 text-center white--text"
        cols="12"
      >
        {{ new Date().getFullYear() }} — <strong>Vuetify</strong>
      </v-col>
    </v-row>
  </v-footer>
  </v-app>
</template>

<script>


export default {
  name: 'App',

  components: {
  },

  data: () => ({
    showPassword:false,
    links:['Home','About','Team Member','Gallery']
  }),
};
</script>
