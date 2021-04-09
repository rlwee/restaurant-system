<template>
  <div class="parent-product col-lg-3">
    <img
      :src="require(`@/assets/images/Products/${product.image}`)"
      alt="Best Selling foods"
      @click.prevent.stop="selectProduct"
      :class="{
        selected: productSelected,
        unselected: !productSelected,
      }"
    />
    <p class="product-name">
      {{ product.productName }}
    </p>

    <FoodModal
      v-if="isModalVisible"
      :close-modal="closeModal"
      :product="product"
      :update-product-modal="updateProduct"
    >
    </FoodModal>

    <!-- {{ JSON.stringify(product.productDescription, null, 4) }} -->
  </div>
</template>

<script>
import FoodModal from "@/components/Modal/FoodModal.vue";
export default {
  name: "Productitem.vue",
  components: {
    FoodModal,
  },
  data() {
    return {
      productSelected: false,
      isActive: false,
      isModalVisible: false,
      productName: "",
      productDescription: "",
    };
  },

  props: {
    product: {
      default: () => {},
      type: Object,
    },
    updateProduct: {
      default: () => {
        return true;
      },
      type: Function,
    },
  },

  methods: {
    selectProduct() {
      this.productSelected = !this.productSelected;
      this.showModal();
      console.log("Selected?", this.productSelected);
    },
    showModal() {
      this.isModalVisible = true;
      console.log("isVIsibile", this.isModalVisible);
    },
    closeModal() {
      this.isModalVisible = false;
      console.log("close", this.isModalVisible);
    },
    updateDescription() {
      this.updateProduct(this.productName, this.productDescription);
    },
  },
  created() {
    this.productName = this.product.productName;
    this.productDescription = this.product.productDescription;
  },
};
</script>

<style>
.food-column-image {
  height: 210px;
  width: 220px;
  border-radius: 50%;
  padding: 0px;
  margin-right: 12px;
}
.selected {
  height: 210px;
  width: 220px;
  border-radius: 50%;
  padding: 0px;
  margin-right: 12px;
  border: 3px solid green;
}
.unselected {
  height: 210px;
  width: 220px;
  border-radius: 50%;
  padding: 0px;
  margin-right: 12px;
}

.parent-product {
  height: 250px;
}
.product-name {
  position: relative;
  bottom: 0px;
}
</style>
