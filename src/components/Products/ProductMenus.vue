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
          :update-product="updateProduct"
          class="row justify-content-center food-image-container"
        >
        </ProductItem>
      </div>
    </div>
    <div class="container-fluid foods-container">
      <div class="row justify-content-center foods-row-container">
        <div class="col-lg-8 foods-column-container">
          <h1>Goodies you will surely</h1>
          <p class="rotatingText">
            <span class="rotatingText-adjective">love</span>
            <span class="rotatingText-adjective">crave</span>
            <span class="rotatingText-adjective">remember</span>
          </p>
        </div>
      </div>
      <div class="row justify-content-center foods-form-row">
        <div class="col-lg-8 foods-form-column">
          <FoodForm
            :key="food"
            :new-product="createProduct"
          >
          </FoodForm>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import ProductItem from "./ProductItem.vue";
import FoodForm from "../Forms/FoodForm.vue";
export default {
  name: "ProductMenus",
  components: {
    ProductItem,
    FoodForm,
  },
  data() {
    return {
      foodList: [
        {
          productName: "Chicken Parmesan",
          productDescription: "This is a chicken parmesan, so yummy!",
          productPrice: 100,
          image: "chickenParmesan.jpg",
        },
        {
          productName: "Chilli Cheese Bowl",
          productDescription: "This is very chilly bowl, so yummy!",
          productPrice: 150,
          image: "chiliCheese.jpg",
        },
        {
          productName: "3Ms Giniling Special",
          productDescription: "2 Rice, 1 Giniling, then Monggos toppings",
          productPrice: 60,
          image: "Giniling.jpg",
        },
        {
          productName: "Roasted Chicken BBQ",
          productDescription: "Dito sa paborito, balik-balikan mo!",
          productPrice: 90,
          image: "chickenBarbecue.jpg",
        },
        {
          productName: "Minute Burger Pizza Flavor",
          productDescription: "Basta lami ni sya na burger ug affordable",
          productPrice: 100,
          image: "burger.jpg",
        },
        {
          productName: "Chicken Curry Indian Flavor",
          productDescription: "Mapapa-sayaw ka talaga sa unang kagat!",
          productPrice: 100,
          image: "chickenCurry.png",
        },
        {
          productName: "Hotdog",
          productDescription: "HA? HAkdog mo na yan!",
          productPrice: 100,
          image: "hotdogs.jpg",
        },
        {
          productName: "Salmon",
          productDescription: "Gains !!",
          productPrice: 100,
          image: "salmon.jpg",
        },
      ],
    };
  },
  methods: {
    updateProduct(foodName, productDescription) {
      const foundItem = this.foodList.find(
        (food) => food.productName === foodName
      );
      foundItem.productDescription = productDescription;
      const filteredItem = this.foodList.filter(
        (food) => food.productName !== foodName
      );
      this.foodList = filteredItem;
      this.foodList.push(foundItem);
      console.log("test", foundItem);
    },

    createProduct(createfoodName, createproductDescription, createproductPrice, createproductImage) {
      const newFood = this.foodList;
      newFood.productName.push(createfoodName);
      newFood.productDescription.push(createproductDescription);
      newFood.productPrice.push(createproductPrice);
      newFood.image.push(createproductImage);
      console.log(newFood, 'updated')

    },
  },
};
</script>

<style lang="scss">
p {
  margin: 0;
}
.food-column {
}

.product-parent-container {
  /* border: 2px solid black; */
}

.products-row-container {
  /* border: 2px solid orange; */
}

.products-column-container {
  /* border: 2px solid green; */
  text-align: center;
}

.products-container {
  /* border: 2px solid pink; */
  margin-top: 150px;
  margin-bottom: 50px;
}

.header-text {
  font-family: "Montserrat", sans-serif;
  font-weight: bold;
}

.food-image-container {
  /* border: 2px solid pink; */
  display: inline-flex;
}

.food-image-container {
  /* border: 2px solid pink; */
  display: inline-flex;
}

.foods-container {
  background-color: #fafafa;
  height: 100vh;

  .foods-row-container {
    margin-top: 50px;
    padding-top: 30px;
    .foods-column-container {
      text-align: center;

      .rotatingText {
        .rotatingText-adjective {
          position: absolute;
          top: -5px;
          left: 230px;
          font-size: 40px;
          opacity: 0;
          &:nth-child(1) {
            left: 860px;
          }
          &:nth-child(2) {
            left: 860px;
          }
          &:nth-child(3) {
            left: 860px;
          }
        }
        .rotatingText-adjective:nth-of-type(1) {
          animation-name: rotate;
          animation-duration: 1.5s;
          animation-delay: 2s;
          animation: rotate 5s infinite;
        }

        .rotatingText-adjective:nth-of-type(2) {
          animation-name: rotate-second;
          animation-duration: 1.5s;
          animation-delay: 2s;
          animation: rotate-second 5s infinite;
        }

        .rotatingText-adjective:nth-of-type(3) {
          animation-name: rotate-three;
          animation-duration: 1.5s;
          animation-delay: 2s;
          animation: rotate-three 5s infinite;
        }
        @keyframes rotate {
          10% {
            opacity: 0;
            transform: translate3d(0, 50px, 0);
          }

          30% {
            opacity: 1;
            color: #007db6;
            transform: translate3d(0, 0, 0);
          }

          40% {
            opacity: 0;
            transform: translate3d(0, -25px, 0);
          }
        }

        @keyframes rotate-second {
          30% {
            opacity: 0;
            transform: translate3d(0, 50px, 0);
          }

          60% {
            opacity: 1;
            color: #ffe400;
            z-index: 111;
            transform: translate3d(0, 0, 0);
          }

          70% {
            opacity: 0;
            transform: translate3d(0, -25px, 0);
          }
        }

        @keyframes rotate-three {
          60% {
            opacity: 0;
            transform: translate3d(0, 50px, 0);
          }

          90% {
            opacity: 1;
            color: #ff4b4b;
            transform: translate3d(0, 0, 0);
          }

          100% {
            opacity: 0;
            transform: translate3d(0, -25px, 0);
          }
        }
      }
    }
  }

  .foods-form-row {
    padding-top: 30px;

    .foods-form-column {
      border-top: 1px solid black;
    }
  }
}
</style>
