<template>

    <div class="parent-product col-lg-3">
        <img 
            :src="require(`@/assets/images/Products/${product.image}`)" 
            alt="Best Selling foods"
            class=" food-column-image" 
        >
        <p class="product-name">
            {{ product.productName }}
        </p>
    </div>
    
    


</template>

<script>
export default {

    props: {
        product: {
        default: () => {},
        type: Object
        },
    }

}
</script>

<style>
.food-column-image{
    height: 210px;
    width: 220px;
    border-radius: 50%;
    padding: 0px;
    margin-right: 12px;
}
.food-column-image:hover{
    border: 3px solid green;
}
.parent-product{
    height: 250px;
}
.product-name{
    position: relative;
    bottom: 0px;
}

</style>