<template lang="pug">
v-container(fluid)
  v-layout(text-center)
    v-flex.xs-12
      v-card(v-for='account in accounts' :key='account.title')
        v-card-title {{account.title}}
        v-card-actions
          v-btn(icon @click='account.show = !account.show')
            v-icon {{account.show ? 'mdi-chevron-up' : 'mdi-chevron-down'}}
        v-expand-transition
          div(v-show='account.show')
            v-sparkline(:fill='false' :gradient='gradient' :value='total' :line-width='5' auto-draw dark)

</template>

<script>
import PugTest from './PugTest.vue'

var _total = [3, 30, 9, 17, 21, 13, 13, 15, 24, 29];

export default {
  components: {
    PugTest
  },
  data: () => ({
    gradient: ['red', 'purple'],
    accounts: [
      { title: 'Groceries' , show: true, value: [1, 2, 3, 4, 5, 6, 7, 8, 9, 10] },
      { title: 'Spending' , show: true, value: [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]  },
      { title: 'Other' , show: true, value: [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]  },
    ],
  }),
  computed: {
    total: () => {
      return _total;
    }
  },
  methods: {
    addOne() {
      _total[0] += 1;
    }
  }
};
</script>
