<template>
  <v-app>
    <v-navigation-drawer
      v-model="drawer"
      :clipped="clipped"
      fixed
      app
    >
      <v-list>
        <v-list-item
          v-for="(item, i) in items"
          :key="i"
          :to="item.to"
          router
          exact
        >
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title v-text="item.title" />
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar
      :clipped-left="clipped"
      fixed
      app
    >
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <v-toolbar-title v-text="title" />
      <v-spacer />
      <v-btn @click="$vuetify.theme.dark=!$vuetify.theme.dark"><v-icon>mdi-invert-colors</v-icon>Dark/light mode</v-btn>
    </v-app-bar>
    <v-main>
      <v-container>
        <Nuxt />
      </v-container>
    </v-main>

    <v-footer
      :absolute="!fixed"
      app
    >
      <span>&copy; {{ new Date().getFullYear() }}</span>
    </v-footer>
  </v-app>
  
</template>

<script>
export default {
  data () {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: 'mdi-home',
          title: 'Strona główna',
          to: '/'
        },
        {
          icon: 'mdi-offer',
          title: 'Oferty pracy',
          to: '/jobs'
        },
        {
          title: 'Edytuj profil',
          to: '/addProfile'
        },
        {
          title: 'Lista pracodawców',
          to: 'profileList'
        },
        {
          title: 'Dodaj ofertę',
          to: 'addJob'
        }
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'CMSPracujemy'
    }
  }
}
</script>




