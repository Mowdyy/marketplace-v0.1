<template>
  <div id="shopping-cart">
    <p class="count" v-if="cartCount > 1">Vous avez {{ cartCount }} articles dans votre panier.</p>
    <p class="count" v-else-if="cartCount == 1">Vous avez {{ cartCount }} article dans votre panier.</p>
    <p class="count" v-else>Vous n'avez aucun article dans votre panier.</p>

    <div class="cart">
        <div v-for="(item, index) in cart" :key="index">
            <div>
                <img class="cartImg" :src="item.productPicture" alt />
            </div>
            <div>
                <p class="count">{{ item.productName }}</p>
            </div>
            <div>
                <p class="count">1</p>
            </div>
            <div>
                <p class="count">{{ item.productPrice + "€" }}</p>
            </div>
            <div>
                <button class="add" @click="removeItem(index)">Retirer l'article</button>
            </div>
      </div>
      <button class="add order" @click="order()">Commander</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "MyCart",
  computed: {
    StoreCart() {
      return this.$store.getters.StoreCart;
    },

    cartCount() {
      return this.StoreCart.length;
    },

    cart() {
        console.log(this.$store.getters.StoreCart)
      return this.$store.getters.StoreCart.map(cartitems => {
        return this.$store.getters.products.find(itemForSale => {
          return cartitems === itemForSale.productId;
        });
      });
    }
  },

  methods: {
    removeItem(index) {
      this.$store.dispatch("removeItem", index);
    },
    order() {
        window.alert("Bouton fictif hihi");
    }
  }
};

</script>