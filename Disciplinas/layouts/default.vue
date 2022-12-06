<template>
  <v-app light>
    <v-navigation-drawer
      v-model="drawer"
      :mini-variant="miniVariant"
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
      class="primary"
      dark
    >
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <v-toolbar-title v-text="title" />
      <v-spacer />
      
    </v-app-bar>
    <v-main>
      <v-container>
        <Nuxt />
      </v-container>
    </v-main>
    <v-navigation-drawer
      v-model="rightDrawer"
      :right="right"
      temporary
      fixed
    >
      <v-list>
        <v-list-item @click.native="right = !right">
          <v-list-item-action>
            <v-icon light>
              mdi-repeat
            </v-icon>
          </v-list-item-action>
          <v-list-item-title>Switch drawer (click me)</v-list-item-title>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-footer
      :absolute="!fixed"
      app
      class="mt-20"
    >
      <span>&copy; {{ new Date().getFullYear() }} Paulino Tyova Todos os direitos reservados</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  name: 'DefaultLayout',
  data () {
    return {
      clipped: true,
      drawer: false,
      fixed: true,
      items: [
        {
          icon: 'mdi-apps',
          title: 'Inicio',
          to: '/'
        },
        {
          icon: 'mdi-apps',
          title: 'Teste',
          to: '/teste'
        },
        {
          icon: 'mdi-apps',
          title: 'Albegra Linear',
          to: '/inspire'
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'Física',
          to: '/inspire'
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'Análise Matemática',
          to: '/inspire'
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'MIC',
          to: '/inspire'
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'Int. Programação',
          to: '/inspire'
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'Int. Informática',
          to: '/inspire'
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'sobre',
          to: '/inspire'
        },
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'Paulino Tyova'
    }
  }
}
</script>
