<template lang="pug">
v-container(fluid class='grey darken-4')
  v-layout(text-center)
    v-flex.xs-6
      account-dashboard(v-for='account in accounts' v-bind:key='account.title' v-bind:account='account')
</template>

<script>
import AccountDashboard from './AccountDashboard.vue'

export default {
  components: {
    AccountDashboard
  },
  data: () => ({
    accounts: [
      { title: 'Groceries' , show: true, value: [1, 2, 3, 4, 5, 6, 37, 8, 9, 10] },
      { title: 'Spending' , show: false, value: [1, 2, 3, 4, 5, 26, 7, 8, 9, 10]  },
      { title: 'Other' , show: false, value: [1, 2, 3, 4, 5, 16, 7, 8, 9, 10]  },
    ],
  }),
};
</script>