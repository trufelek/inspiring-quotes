<template>
    <div class="quotes-grid row">
        <app-quote v-for="(quote, i) in quotes" :key="i" @click.native="deleteQuote(i)">{{ quote }}</app-quote>
    </div>
</template>

<script>
    import appQuote from './Quote'

    export default {
        props: ['quotes'],
        components: {
            appQuote
        },
        methods: {
            deleteQuote(i) {
                this.$emit('quoteDeleted', i);
            }
        }
    }
</script>

<style>
</style>
