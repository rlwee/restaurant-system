<template>
  <div class="container-fluid food-container">
    <div class="row justify-content-center food-row">
      <div class="col-lg-6 food-column">
          {{ JSON.stringify(productName, null, 4) }}
        <p>Want Something? We Got It !</p>
        <form @submit.prevent="submitForm">
          <label for="name">Your Favourite Meal</label> <br />
          <input id="name" class="form-input" type="text" v-model="productName" /> <br />
          <label for="description">Description</label> <br />
          <input id="description" class="form-input" type="text" v-model="productDescription" /> <br />
          <label for="price">Price</label> <br />
          <input id="price" class="form-input" type="text" v-model="productPrice" /> <br />
          <label for="price">Image</label> <br />
          <input id="price" class="form-input" type="text" v-model="image" /> <br />
          <button
            @click="createNewProduct"
            >create
          </button>
        </form>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "FoodForm",
  components: {},
  data() {
    return {
      productName: "",
      productDescription: "",
      productPrice: "",
      image:""
    };
  },
  props: {
    product: {
      default: () => {},
      type: Object,
    },
    newProduct: {
      default: () => {
        return true;
      },
      type: Function,
    },
  },
  methods: {
    createNewProduct() {
      this.newProduct(
        this.productName,
        this.productDescription,
        this.productPrice,
        this.image
      );
    },
    submitForm(event){
            event.preventDefault()
        }
  },
};
</script>

<style lang="scss">
.food-container {
  .food-row {
    .food-column {
      text-align: center;
      margin-top: 40px;
      padding-bottom: 20px;

      p {
        font-family: "Montserrat", sans-serif;
        font-weight: bold;
      }

      form {
        border: 2px solid #0b6623;
        border-radius: 2%;
        text-align: center;
        width: 100%;
        height: 60vh;
        margin-top: 20px;

        label {
          margin-top: 50px;
        }

        .form-input {
          border: none;
          border-bottom: 1px solid black;
          outline: none;
          width: 80%;
          margin-top: 20px;
        }
      }
    }
  }
}
</style>
