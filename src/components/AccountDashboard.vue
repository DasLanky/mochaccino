<template lang="pug">
v-layout
    v-flex.xs-12
        v-card.my-4(dark)
            v-card-title {{account.title}}
                v-spacer
                v-btn(icon @click='account.show = !account.show')
                    v-icon {{account.show ? 'mdi-chevron-up' : 'mdi-chevron-down'}}
            v-expand-transition
                div(v-show='account.show')
                    v-layout(row)
                        v-flex.xs-6
                            v-layout(column)
                                v-flex(xs-12)
                                    span Total: {{account.value[0]}}
                                v-flex(xs-12)
                                    span Total: {{account.value[0]}}
                                v-flex(xs-12)
                                    span Total: {{account.value[0]}}
                        v-flex.xs-6
                            v-sparkline(:fill='false' smooth :gradient='gradient' :value='account.value' :line-width='2' :auto-draw-duration='1000' auto-draw dark)
            v-card-actions
                v-btn(round)
                    v-icon mdi-icon-left
                    span Expense
                v-btn(round)
                    v-icon mdi-icon-left
                    span Income
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
    props: [
        'account'
    ],
    data() {
        return {
            gradient: ['#42b3f4'],
        };
    }
})
</script>

<style lang="stylus">

</style>