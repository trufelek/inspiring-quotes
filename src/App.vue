<template>
    <div class="container">
        <app-header :quotesCount="quotes.length" :maxQuotes="maxQuotes"></app-header>
        <new-quote @quoteAdded="newQuote"></new-quote>
        <quotes :quotes="quotes" @quoteDeleted="deleteQuote"></quotes>
        <div class="row">
            <div class="col-sm-12 text-center">
                <div class="alert alert-info">Click on a Quote to delete it!</div>
            </div>
        </div>
    </div>
</template>

<script>
    import appHeader from './components/Header'
    import Quotes from './components/Quotes'
    import NewQuote from './components/NewQuote'

    export default {
        data() {
            return {
                quotes: [
                    'Just a Quote to see something'
                ],
                maxQuotes: 10
            }
        },
        components: {
            appHeader,
            NewQuote,
            Quotes
        },
        methods: {
            newQuote(q) {
                if(this.quotes.length >= this.maxQuotes) {
                  return alert('Please remove some quotes!')
                }

                this.quotes.push(q);
            },
            deleteQuote(i) {
                this.quotes.splice(i, 1);
            }
        }
    }
</script>

<style>
</style>
