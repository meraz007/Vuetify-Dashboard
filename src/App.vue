<template>
  <v-app>
    <v-app-bar app color="primary" dark>
      <v-toolbar-title style="cursor: pointer" @click="$router.push('/')">
      Vuetify Deshboard</v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn 
        v-for="link in links"
        :key="`${link.label}-header-link`"
        text
        rounded 
        :to="link.url">
        {{link.label}}
      </v-btn>

    </v-app-bar>
    <!-- Log In page-->
    <v-content>
  <router-view></router-view>
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
        :key="`${link.label}-footer-link`"
        color="white"
        text
        rounded
        :to="link.url"
        class="my-2"
      >
        {{ link.label }}
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
    links:[
      {
        label:'home',
        url:"/"
      },
      {
        label:'login',
        url:'/login'
      },
      {
        label:'deshboard',
        url:'/deshboard'
      }
    ]
  }),
};
</script>