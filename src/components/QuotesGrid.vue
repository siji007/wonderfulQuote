<template>
    <div class="row">
        <appQuote v-for="quote in quotes" :key="(quote,index)" @click.native="deleteQuote"> <!--WHAT THE native modifier does is,it tells vue js is react to a click  on that component if it happens on the native element of this component ,so it will basically register a click here -->
            
            {{quote}}

        </appQuote>
        
    </div>
</template>
<script>
import Quote from './Quotes'
export default {
    components:{

        appQuote:Quote
    },
    props: ['quotes'],
    methods:{
        deleteQuote(index) {
            this.$emit('quoteDeleted', index );
        }
    }
}
    
</script>
<style  scoped>

</style>