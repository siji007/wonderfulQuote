<template>
    <div class="row">
       <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3">
           <label for="">Quote</label>
           <textarea v-model="quote" class="form-control" name="" id="" cols="30" rows="3"></textarea>
       </div> 

       <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3">
           <button @click.prevent="createNew" class="btn btn-primary">Add Quote</button>  <!--we don't the page to reload whenever we are submitting our file that is why we use the "@click.prevent" method-->
       </div> 
        
    </div>
</template>
<script>

export default {
    data: function() {
        return {
            quote: ''
        }
    },
    methods:{
        createNew(){
            this.$emit('quoteAdded', this.quote);
            this.quote = '';
        }
    }

}
    
</script>
<style scoped>

</style>