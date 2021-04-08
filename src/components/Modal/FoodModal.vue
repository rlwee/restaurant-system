<template>
  <transition name="modal-fade">
    <div class="modal-backdrop">
      <div class="back" @click="closeModal"></div>
      <div class="modal" role="dialog">
        <header class="modal-header" id="modalTitle">
          <p name="header" class="slot-text">We Deliver!</p>
          <button type="button" class="btn-close" @click="closeModal">x</button>
        </header>

        <section class="modal-body" id="modalDescription">
          <div class="left-content-image">
            <img
              :src="require(`@/assets/images/Products/${product.image}`)"
              :alt="product.productName"
              class="product-image"
            />
          </div>
          <div class="right-content-details">
            <p>{{ product.productDescription }}</p>

            {{ JSON.stringify(product.productName, null, 4) }}
            <form>
              <div>
                <label for="productDescription">
                  {{ product.productDescription }}
                </label>
                <!-- prettier-ignore -->
                <input 
                    type="text" 
                    id="productDescription" 
                    v-bind:product="product.productDescription"
                    v-model="product.productDescription"
                    >
              </div>
              <div>
                <button>Submit</button>
              </div>
            </form>

            <p>Dish: {{ product.productName }}</p>
            <p>For Only: {{ product.productPrice }}php</p>
          </div>
        </section>
      </div>
    </div>
  </transition>
</template>

<script>
export default {
  name: "FoodModal",

  data() {
    return {};
  },
  methods: {},

  props: {
    closeModal: {
      default: () => {
        return true;
      },
      type: Function,
    },
    product: {
      default: () => {},
      type: Object,
    },
  },
};
</script>

<style>
.modal-backdrop {
  position: fixed;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  background-color: rgba(0, 0, 0, 0.3);
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 500;
}

.back {
  width: 100%;
  height: 100%;
  position: absolute;
  z-index: 800;
}

.modal {
  z-index: 100000;
  background: #ffffff;
  box-shadow: 2px 2px 20px 1px;
  overflow-x: auto;
  display: block;
  flex-direction: column;
  width: 800px;
  height: 400px;
  position: relative;
  transition: opacity 0.5s ease ease-in-out;
}

.modal-header,
.modal-footer {
  padding: 15px;
  display: flex;
}

.slot-text {
  text-align: center;
  width: 100%;
  font-size: 20px;
}

.modal-header {
  position: relative;
  border-bottom: 1px solid #eeeeee;
  color: #4aae9b;
  justify-content: space-between;
  text-align: center;
}

.modal-footer {
  border-top: 1px solid #eeeeee;
  flex-direction: column;
  justify-content: flex-end;
}

.modal-body {
  position: relative;
  padding: 20px 10px;
  height: 100%;
  display: flex;
}

.left-content-image {
  width: 40%;
  height: 80%;
}

.product-image {
  width: 310px;
  height: 300px;
}

.right-content-details {
  font-family: "Montserrat", sans-serif;
  width: 60%;
  height: 84%;
  text-align: left;
  font-weight: bold;
  padding-left: 20px;
}

.btn-close {
  position: absolute;
  top: 0;
  right: 0;
  border: none;
  font-size: 20px;
  padding: 10px;
  cursor: pointer;
  font-weight: bold;
  color: #4aae9b;
  background: transparent;
}

.btn-green {
  color: white;
  background: #4aae9b;
  border: 1px solid #4aae9b;
  border-radius: 2px;
}
</style>
