<template>
  <div>
    <ProductMenus></ProductMenus>
    <Foods></Foods>
  </div>
</template>

<script>
import ProductMenus from "../components/Products/ProductMenus.vue";
import Foods from "../components/Displays/Foods.vue";
export default {
  name: "Product",
  components: {
    ProductMenus,
    Foods,
  },
};
</script>

<style></style>
