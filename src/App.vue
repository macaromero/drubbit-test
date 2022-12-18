<template id="app">
  <v-app>
      <NavbarVue/>
    <v-main id="main">
      <SelectedProductVue class="mb-9"/>
      <ProductsVue/>
    </v-main>
      <FooterVue/>
      <ContactButton id="sticky-element"/>
  </v-app>
</template>

<style>
  #app {
    font-family: 'Proxima Nova',sans-serif;
    background-color: #e4e4e4;
  }

  #main {
    margin-top: 7rem;
  }

  #sticky-element {
    position: sticky;
    bottom: 1rem;
    right: 1rem;
    align-self: flex-end;
  }

</style>

<script>
import ContactButton from './components/ContactButton.vue';
import FooterVue from './components/Footer.vue';
import NavbarVue from './components/Navbar.vue';
import ProductsVue from './components/Products.vue';
import SelectedProductVue from './components/SelectedProduct.vue';

export default {
  name: 'App',

  components: {
    NavbarVue,
    FooterVue,
    ProductsVue,
    SelectedProductVue,
    ContactButton
  }
};
</script>
