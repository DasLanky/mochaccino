<template lang="pug">
v-container
  v-layout(text-center row no-wrap)
    v-flex.xs-12
        v-list(nav left dense)
          v-list-item(dense v-for='account in accounts' :key='account.title' ripple)
            v-list-item-title {{account.title}}

  v-layout(text-center wrap)
    v-flex(xs12)
      pug-test
      v-img.my-3(:src="require('../assets/logo.svg')" contain height="200")

</template>

<script>
import PugTest from './PugTest.vue'
export default {
  components: {
    PugTest
  },
  data: () => ({
    accounts: [
      { title: 'Groceries' },
      { title: 'Spending' },
      { title: 'Other' },
    ],
  }),
};
</script>
