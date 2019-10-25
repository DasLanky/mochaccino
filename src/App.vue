<template lang="pug">
v-app
  v-app-bar(app)
    v-toolbar-title.headline.text-uppercase
      span Mochaccino
    v-spacer
    v-btn(text href="https://github.com/vuetifyjs/vuetify/releases/latest" target="_blank")
      span.mr-2 Latest Release
  v-content
    main-view
</template>

<script>
import MainView from './components/MainView';

export default {
  name: 'App',
  components: {
    MainView,
  },
  data: () => ({
    //
  }),
};
</script>
