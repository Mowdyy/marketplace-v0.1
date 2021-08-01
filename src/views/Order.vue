<template>
    <div>
        <h1>Produits disponibles</h1>
        <div class="row">
            <div class="col-4 products" v-for="product in products" :key="product">
                <img :src="product.productPicture">
                <p>
                    {{ product.productName }}
                </p>
                <p>
                    <b>{{ product.productPrice }}€</b>
                </p>
                <button class="add" @click="addItem(product.productId)">Ajouter au panier</button>
            </div>
        </div>
    </div>
</template>

<script>
import productsData from "../../products.json";
import MyCart from '@/components/MyCart.vue';

export default {
  name: 'Order',
  props: ["id", "name", "picture", "price"],
  components: {
    MyCart
  },
  data: () => {
    return {
      products: productsData,
    }
  },
  methods: {
    addItem(id) {
      this.$store.dispatch("addItem", id);
    }
  },
}
</script>