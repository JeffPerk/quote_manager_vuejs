<template>
    <div class="row">
        <div>
            <app-quote v-for="(quote, index) in quotes" @click.native="deleteQuote(index)">{{ quote }}</app-quote>  <!-- the @click.native modifier allows the behavior of the single quote be functional on the parent  -->
        </div>
    </div>
</template>

<script>
    import Quote from './Quote.vue';

    export default {
      props: ['quotes'],
      components: {
        appQuote: Quote
      },
      methods: {
        deleteQuote(index) {
          this.$emit('quoteDeleted', index);
        }
      }
    }
</script>

<style>

</style>