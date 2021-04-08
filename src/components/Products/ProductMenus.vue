<template>
  <div class="container-fluid product-parent-container">
    <div class="row justify-content-center products-row-container">
        <div class="col-lg-8 products-column-container">
            <div class="row justify-content-center products-container">
                <h2 class="header-text">Our Best Sellers !</h2>
            </div>
            <ProductItem
                v-for="food in foodList" 
                :key="food"
                :product="food"
                class="row justify-content-center food-image-container"
            >

            </ProductItem>
        </div>
    </div>
  </div>
</template>

<script>
import ProductItem from './ProductItem.vue';
export default {
    name: 'ProductMenus',
    components: {
        ProductItem
    },
    data(){
        return{
                foodList: [
                    {
                        productName: 'Chicken Parmesan',
                        productDescription: 'This is a chicken parmesan, so yummy!',
                        productPrice: 100,
                        image: 'chickenParmesan.jpg'
                    },
                    {
                        productName: 'Chilli Cheese Bowl',
                        productDescription: 'This is very chilly bowl, so yummy!',
                        productPrice: 150,
                        image: 'chiliCheese.jpg'
                    },
                    {
                        productName: '3Ms Giniling Special',
                        productDescription: '2 Rice, 1 Giniling, then Monggos toppings',
                        productPrice: 60,
                        image: 'Giniling.jpg'
                    },
                    {
                        productName: 'Roasted Chicken BBQ',
                        productDescription: 'Dito sa paborito, balik-balikan mo!',
                        productPrice: 90,
                        image: 'chickenBarbecue.jpg'
                    },
                    {
                        productName: 'Minute Burger Pizza Flavor',
                        productDescription: 'Basta lami ni sya na burger ug affordable',
                        productPrice: 100,
                        image: 'burger.jpg'
                    },
                    {
                        productName: 'Chicken Curry Indian Flavor',
                        productDescription: 'Mapapa-sayaw ka talaga sa unang kagat!',
                        productPrice: 100,
                        image: 'chickenCurry.png'
                    },
                    {
                        productName: 'Hotdog',
                        productDescription: 'HA? HAkdog mo na yan!',
                        productPrice: 100,
                        image: 'hotdogs.jpg'
                    },
                    {
                        productName: 'Salmon',
                        productDescription: 'Gains !!',
                        productPrice: 100,
                        image: 'salmon.jpg'
                    },
            ]
        };
    },

}
</script>

<style>
p{
    margin: 0;
}
.food-column{
}

.product-parent-container{
    /* border: 2px solid black; */
}

.products-row-container{
    /* border: 2px solid orange; */
}

.products-column-container{
    /* border: 2px solid green; */
    text-align: center;
}

.products-container{
    /* border: 2px solid pink; */
    margin-top: 80px;
    margin-bottom: 50px;
}


.header-text{
    font-family: 'Montserrat', sans-serif;
    font-weight: bold;
}

.food-image-container{
    /* border: 2px solid pink; */
    display: inline-flex;
}


</style>