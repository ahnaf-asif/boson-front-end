<template>
  <v-app>
    <v-app-bar :clipped-left="clipped" fixed app flat elevation="1" color="white">
      <NuxtLink class="nav-link-item" to="/">
        <v-toolbar-title v-text="title" class="nav-title" />
      </NuxtLink>
      <v-spacer />

      <DesktopNavLinks></DesktopNavLinks>
      <v-btn v-if="$vuetify.breakpoint.xsOnly || $vuetify.breakpoint.smOnly " icon @click.stop="rightDrawer = !rightDrawer" >
        <v-icon>mdi-menu</v-icon>
      </v-btn>
    </v-app-bar>
    <v-main>
      <v-container>
        <Nuxt />
      </v-container>
    </v-main>

    <v-navigation-drawer v-if="$vuetify.breakpoint.xsOnly || $vuetify.breakpoint.smOnly" v-model="rightDrawer" :right="right" temporary fixed>
      <MobileNavLinks></MobileNavLinks>
    </v-navigation-drawer>

    <v-footer :absolute="!fixed" app color="blue-grey darken-4 white--text" class="py-10">
      <v-row> 
        <v-col cols="12" md="5">
          <h1 class="mb-10">Let's work Together</h1>
          <p style="max-width: 50ch;">Our club is open for School, College and University going students all over the country. We work on different olympiads, Scientific Magazine, publishing blogs and many other things. We organize Mega festivals, various Olympiads and competitions. We also organize camps and seminars.</p>
          <p>Please Join us Here if you haven't already.</p>
        </v-col>
        <v-col cols="12" md="3">
          <h1 class="mb-10 text-center">Quick Links</h1>
          <v-row>
            <v-col cols="6" style="">
              <ul>
                <li>List Item 1</li>
              </ul>
            </v-col>
            <v-col cols="6" style="text-align:right;">
              <ul class="" >
                <li>List item 2</li>
              </ul>
            </v-col>
          </v-row>
        </v-col>
        <v-col>
          <h1 class="text-center mb-10">Contact Us</h1>
          <p class="text-center">+880 1633923851</p>
          <p class="text-center">bosonbiggansangho@gmail.com</p>
          <p class="text-center">Leave us a message here.</p>
        </v-col>
      </v-row>
    </v-footer>
  </v-app>
</template>

<style lang="scss">
.nav-title{
  font-size: 24px !important;
  //font-weight: bold;
  &:hover{
    color: darkblue;
  }
}
.nav-link{
  display: flex;
  color: red;
}
.nav-link-item{
  color: black !important;
  text-decoration: none;
  //font-size: 1.2em;
  &:hover{
    color: darkorange !important;
  }
}
.navbar-v-menu{
  border: 2px solid darkorange !important;
}
ul{
  list-style: none;
}
</style>


<script>
import DesktopNavLinks from '/components/DesktopNavLinks';
import MobileNavLinks from '/components/MobileNavLinks';

export default {
  components: {MobileNavLinks, DesktopNavLinks},
  data () {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      rightDrawer: false,
      title: 'Boson Science Club',
      items: [
        {
          'title': 'hello world'
        }
      ]
    }
  },
  methods: {

  }
}
</script>

