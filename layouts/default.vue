<template>
  <v-app dark>
    <v-navigation-drawer
      v-model="drawer"
      :mini-variant="miniVariant"
      :clipped="clipped"
      fixed
      temporary
    >
      <v-list>
        <v-list-item :to="'/'">
          <v-list-item-action>
            <v-icon>mdi-account-tie</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title v-text="'About Me'" />
          </v-list-item-content>
        </v-list-item>
        <v-list-item>
          <v-list-item-action>
            <v-icon>mdi-apps-box</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title v-text="'Demos'" />
          </v-list-item-content>
        </v-list-item>
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
    <v-app-bar :clipped-left="clipped" fixed app>
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <v-toolbar-title v-text="title" />
      <v-spacer />
      <v-switch
        :value="darkMode"
        @change="toggleDarkMode"
        :label="`toggle ${switchLabel} mode`"
        class="mt-5"
      ></v-switch>
    </v-app-bar>
    <v-main>
      <v-container>
        <Nuxt />
      </v-container>
    </v-main>
    <v-footer :absolute="!fixed" app>
      <span>&copy; {{ new Date().getFullYear() }}</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  name: 'DefaultLayout',
  data() {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: 'mdi-chart-bubble',
          title: 'Counter Example',
          to: '/inspire',
        },
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'Wilmar Osorio',
      //? dark mode var
      darkMode:false
    }
  },
  methods: {
    toggleDarkMode: function () {
      this.$vuetify.theme.dark = !this.$vuetify.theme.dark
      this.darkMode = !this.darkMode
    },
  },
  computed: {
    switchLabel: function () {
      return this.darkMode ? 'light' : 'dark'
    },
  },
}
</script>
