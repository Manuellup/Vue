<template>
  <div>
      <main id="app">
            
            <section class="items">
                <h4>Pick your items</h4>
                <div v-for="(product, n) in products" :key="n" class="product selected">
                    <div class="photo">
                        <img :src="product.photo">
                    </div>
                    <div class="description">
                        <span class="name">{{product.name}}</span>
                        <span class="price">{{product.price}}</span>
                        <div class="quantity-area">
                            <button @click="minusQuantity(n)">-</button>
                            <span class="quantity">{{product.quantity}}</span>
                            <button @click="addQuantity(n)">+</button>
                        </div>
                    </div>
                </div>
               
            </section>

            <section class="summary">
                <strong>Order Details</strong>
                <table>
                    <thead>
                        <tr>
                            <th>Item</th>
                            <th>Total</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td>1x Big Mac</td>
                            <td>5.99</td>
                        </tr>
                        
                        <tr>
                            <th>Total</th>
                            <th>5.99</th>
                        </tr>
                    </tbody>
                </table>
            </section>

        </main>
  </div>
</template>

<script>
export default {
    data(){
        return {
             products:  [
                {
                    photo: "../images/big-mac.png",
                    name: "Big Mac",
                    price: 5.99,
                    active: false,
                    quantity: 0
                },
                {
                    photo: "../images/mc-chicken.png",
                    name: "Mc Chicken",
                    price: 4.99,
                    active: false,
                    quantity: 0
                },
                {
                    photo: "../images/double-cb.png",
                    name: "Double Cheese Burger",
                    price: 2.99,
                    active: false,
                    quantity: 0
                },
                {
                    photo: "../images/fries.png",
                    name: "Fries",
                    price: 2.99,
                    active: false,
                    quantity: 0
                },
                {
                    photo: "../images/nuggets.png",
                    name: "Mc Nuggets",
                    price: 3.49,
                    active: false,
                    quantity: 0
                },
                {
                    photo: "../images/salad.png",
                    name: "Salad",
                    price: 2.79,
                    active: false,
                    quantity: 0
                },
                {
                    photo: "../images/cola.png",
                    name: "Coke",
                    price: 1.99,
                    active: false,
                    quantity: 0
                },
                {
                    photo: "../images/lipton.png",
                    name: "Ice Tea",
                    price: 1.99,
                    active: false,
                    quantity: 0
                },
                {
                    photo: "../images/water.png",
                    name: "Water",
                    price: 1.49,
                    active: false,
                    quantity: 0
                }
            ]   
        }
    },

    methods: {

     addQuantity(n){
         
         this.products[n].quantity++

               
     },
     minusQuantity(n){
         this.products[n].quantity === 0 ? 0 : this.products[n].quantity--
               
     }
    }


}
</script>

<style>
body {
  margin: 0;
  font-family: "Open Sans", sans-serif;
}

main > section.items h4 {
  text-align: center;
  margin-top: 0;
  width: 100%;
}
main {
  display: flex;
  justify-content: center;
  align-items: flex-start;
  flex-wrap: wrap;
  padding-top: 20px;
}

main > section.items {
  display: flex;
  flex-wrap: wrap;
  border: 1px solid lightgrey;
  padding: 20px;
  max-width: 500px;
  min-width: 300px;
  justify-content: center;
}

section.items .product {
  border: 1px solid lightgrey;
  margin: 6px;
  flex: 0 0 calc(33.333% - 24px);
  cursor: pointer;
  text-align: center;
}

section.items .product.selected {
  border: 2px solid rgb(29, 134, 233);
}

section.items .photo img {
  max-width: 90px;
}

section.items .description {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  font-size: 11px;
  line-height: 15px;
}

section.items .description .price {
  font-weight: bold;
  margin: 4px auto;
}

section.items .description .quantity-area {
  margin: 8px auto;
  height: 14px;
}

section.items .description .quantity-area button {
  width: 16px;
  height: 16px;
  display: inline-flex;
  justify-content: center;
  align-items: center;
  cursor: pointer;
}

section.items .description .quantity-area .quantity {
  font-weight: bold;
  margin: 0 4px;
}

section.summary {
  background-color: rgb(245, 245, 245);
  padding: 20px;
  min-height: 200px;
  min-width: 200px;
  text-align: center;
}

section.summary table {
  width: 100%;
  padding-top: 12px;
  font-size: 11px;
  margin: auto;
}

section.summary table tbody tr:last-of-type th {
  border-top: 1px solid black;
  padding-top: 4px;
}
</style>
