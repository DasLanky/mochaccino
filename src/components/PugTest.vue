<template lang="pug">
v-layout#wrapper
    v-flex(xs12 ma-0)
        v-card(v-for='(account, i) in accounts' :key='account.name')
            v-card-text
                | {{account.name}}
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
    data() {
        return {
            accounts: [
                {
                    name: 'Groceries'
                },
                {
                    name: 'Spending'
                },
            ]
        };
    }
})
</script>

<style lang="stylus">

</style>