<template>
  <v-app>
    <v-navigation-drawer
      persistent
      :mini-variant="miniVariant"
      clipped
      v-model="drawer"
      enable-resize-watcher
      fixed
      app
    >
      <v-list>
        <v-list-tile
          value="true"
          v-for="(item, i) in items"
          :key="i"
        >
          <v-list-tile-action>
            <v-icon v-html="item.icon"></v-icon>
          </v-list-tile-action>
          <v-list-tile-content>
            <v-list-tile-title v-text="item.title"></v-list-tile-title>
          </v-list-tile-content>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>
    <v-toolbar
      app
      color="primary"
      clipped-left
    >
      <v-toolbar-side-icon
        class="secondary--text"
        @click.stop="drawer = !drawer">
      </v-toolbar-side-icon>
      <v-toolbar-title 
        class="secondary--text" 
        v-text="title"
      >
      </v-toolbar-title>
      <v-btn
        flat
        :to="'/'"
        color="secondary"
      >Home
      </v-btn>
      <v-btn
        flat
        :to="'/about'"
        color="secondary"
      >About
      </v-btn>
      <v-spacer></v-spacer>
    </v-toolbar>
    <v-content>
      <router-view/>
    </v-content>
    <v-footer :fixed="fixed" app>
      <span>&copy; 2017</span>
    </v-footer>
  </v-app>
</template>

<script>

export default {
  name: 'App',
  data () {
    return {
      drawer: false,
      fixed: false,
      items: [{
        icon: 'bubble_chart',
        title: 'Inspire'
      }],
      miniVariant: false,
      title: 'James Squared Construction'
    }
  }
}
</script>
