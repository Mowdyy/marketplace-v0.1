<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Nos produits</router-link> |
      <router-link to="/cart">Votre Panier</router-link>
    </div>
    <router-view/>
  </div>
</template>

<style>

#app {
  font-family:'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  letter-spacing: 1px;
}

#app h1 {
  text-align: center;
}

#nav {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}

.products {
  text-align: center;
  padding: 50px;
  margin: 0;
  display: flex;
  flex-direction: column;
  align-items: center;
  border-bottom: 2px solid #42b983;
}

img {
  margin: 20px 0;
  max-width: 250px;
}

div.row {
  margin: 0;
  max-width: 100%;
  text-align: center;
  padding: 50px;
}

.add {
  border-radius: 5px;
  border: 1px solid transparent;
  padding: 10px;
  width: 250px;
  background-color: rgb(192, 192, 192);
}

.add:hover {
  background-color: rgb(231, 231, 231);
  border: 1px solid rgb(192, 192, 192);
}

.add:focus {
  animation: select 1s;
}

.count {
  font-weight: bold;
  text-align: center;
}

@keyframes select {
  0% {
    background-color: green;
  }

  100% {
    pointer-events: none;
    background-color: rgb(192, 192, 192);
  }
}

.cart div{
  width: 100%;
  display: flex;
  flex-direction: row;
  justify-content: space-around;
  align-items: center;
  text-align: center;
}

.cartImg {
    width: 100px;
}

.order {
  position: fixed;
  bottom: 50px;
  right: 50px;
  font-weight: bold;
}

</style>
