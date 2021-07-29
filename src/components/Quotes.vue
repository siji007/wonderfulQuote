<template>
    <div class="col-sm-6 col-md-4 col-lg-3">
        <div class="panel-body quote"> <!--So it will basically register a click here via the native comp declared from Quotes grid-->
            <slot></slot> <!--slot is use for rendering  data from outside and render it in the child component-->
        </div>
        
    </div>
</template>
<script>
export default{
    props: ['quotes']
}
    
</script>
<style  scoped>
.panel-body{
    font-family: 'Arizona', cursive;
    border: 1px solid lightcoral;
    font-size: 32px;
}
.quote{
    cursor: pointer
}

</style>