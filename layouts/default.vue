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

    <v-footer :absolute="!fixed" app >
      <span>&copy; {{ new Date().getFullYear() }}</span>
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

