<template>
  <v-app-bar>
    <v-toolbar-title @click="$router.push('/')">
      Navein's Merch Website
    </v-toolbar-title>
    <v-btn class="btn2" @click="$router.push('/')">Home</v-btn>
    <v-btn class="btn2" @click="$router.push('/about')">About</v-btn>
    <v-btn class="btn2" @click="$router.push('/products')">Products</v-btn>

    <v-spacer></v-spacer>
    <v-btn @click="$router.push('/Cart')" class="text-none" stacked>
      <v-badge :content="cartStore.productsTotal" color="error">
        <v-icon> mdi-cart-outline </v-icon>
      </v-badge>
    </v-btn>
  </v-app-bar>
</template>

<script setup>
import { useCartStore } from "../stores/cart";
const cartStore = useCartStore();
</script>

<style lang="scss" scoped>
.router-link-exact-active {
  color: aquamarine;
}

.btn2:hover {
  border-bottom: 3px solid #e53935;
  padding-bottom: 5px; /* Add bottom padding */
} /* Aquamarine underline on hover */

.btn2 {
  font-size: large;
  font-weight: bold;
}
</style>