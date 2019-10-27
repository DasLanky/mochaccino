<template lang="pug">
v-container(fluid class='black')
  v-layout(text-center)
    v-flex.xs-12
      v-card.my-4(v-for='account in accounts' :key='account.title' dark)
        v-card-title {{account.title}}
          v-spacer
          v-btn(icon @click='account.show = !account.show')
            v-icon {{account.show ? 'mdi-chevron-up' : 'mdi-chevron-down'}}
        v-expand-transition
          div(v-show='account.show')
            v-sparkline(:fill='false' smooth :gradient='gradient' :value='total' :line-width='2' :auto-draw-duration='1000' auto-draw dark)

</template>

<script>
import PugTest from './PugTest.vue'

var _total = [23490, 23487, 23480, 23700, 22495, 24500, 25600, 26899, 27900];

export default {
  components: {
    PugTest
  },
  data: () => ({
    gradient: ['#42b3f4'],
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