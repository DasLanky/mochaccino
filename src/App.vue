<template lang="pug">
v-app
  v-system-bar(app dark)
    v-toolbar-title.headline.text-uppercase
      span Mochaccino
    v-spacer
    v-btn(text href="https://github.com/vuetifyjs/vuetify/releases/latest" target="_blank")
      span.mr-2 Latest Release
  v-navigation-drawer(app permanent left fixed dark class='deep-purple accent-4')
    v-list(dense nav flat)
      v-list-item(v-for='item in items' :key='item.title' link)
        v-list-item-icon
          v-icon {{item.icon}}
          v-list-item-content.mx-3
            v-list-item-title {{item.title}}
  v-content
    main-view
  v-footer(fixed app dark)
    v-spacer
    span.px-3 &copy; 2019 Langston Richard Chandler
</template>

<script>
import MainView from './components/MainView';

export default {
  name: 'App',
  components: {
    MainView,
  },
  data: () => ({
    items: [
      { title: 'Dashboard', icon: 'mdi-cash-usd' }
    ]
  }),
};
</script>
