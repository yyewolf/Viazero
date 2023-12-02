<script>
  let cart = [];
  let products = [
    {
      id: 1,
      name: "Une multiprise 5 prises",
      image: "https://media.ldlc.com/r1600/ld3/zoom/2008/LD0000686046.jpg",
      price: 10,
      quantity: 1,
    },
    {
      id: 2,
      name: "Switch 4 ports",
      image: "/ethernet.jpg",
      price: 11,
      quantity: 1,
    },
    {
      id: 3,
      name: "Super flag",
      image:
        "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSnrLESiIZNkyJehoMpOG9dWvzh8Pip2kUodPbATwj17w&s",
      price: 12,
      quantity: 1,
    },
    {
      id: 3,
      name: "Un code d'inscription",
      image:
        "data:image/jpeg;base64,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tlqKVdQykEEEAgg9QQeolbbc4T0qjFrao1LP3Ma0HkCQR5ZxAsv26hdRIAxnPZOeuI+2Eu9oO9NgyIq01Ycw2nJYg9oyxHpJF/0XXbDQ95lOmnFQrj90viSLYHC+3osHrE1WHMa8aAfBByPrmBG+Fm6jvVF5VQhFz7IEfESMGp5YJA78k90mfFm2Z9mVNIzoZHYfsqw1H0HP0kyoUVQYUYivRV1KsAQQQQeYIPUQOUZLLAmx2fXep7tW7C06aHk3sxnVUI7Bhm+kl22eE4Ll7OsaYzkIwLBf3WBBA+c89nwoqO+q5ui3fpU6j/G5P8pRXWyNl1LuqtGiuWPU/dRe1mPYP59J0NunsBLG3WmnUc2Y9WY/ET/z3T9N392qFkmijTC9pPVmPezHmTN5IMxEQMRMxAREQExMzEBERAzExMwExEQMxEQMREQEREDMxEQEREBMzEQMzERAzExEBERARMxAREQEREBERAREQEREBERAREQEREBERAREQEREBERAREQEREBERAREQEREBERAREQEREBERAREQEREBERAREQEREBERAREQEREBERAREQEREBERAREQEREBERAREQEREBERAREQEREBERAREQEREBERA//2Q==",
      price: 128,
      quantity: 1,
    },
  ];

  const addToCart = (product) => {
    for (let item of cart) {
      if (item.id === product.id) {
        product.quantity += 1;
        cart = cart;
        return;
      }
    }
    cart = [...cart, product];
  };

  const minusItem = (product) => {
    for (let item of cart) {
      if (item.id === product.id) {
        if (product.quantity > 1) {
          product.quantity -= 1;
          cart = cart;
        } else {
          cart = cart.filter((cartItem) => cartItem != product);
        }
        return;
      }
    }
  };

  const plusItem = (product) => {
    for (let item of cart) {
      if (item.id === product.id) {
        item.quantity += 1;
        cart = cart;
        return;
      }
    }
  };

  $: total = cart.reduce((sum, item) => sum + item.price * item.quantity, 0);
</script>

<div class="p-10">
  <p>Vous avez {cart.length} objets dans votre panier</p>
  <div class="product-list">
    {#each products as product}
      <div class="p-4">
        <div class="image" style="background-image: url({product.image})"></div>
        <h4>{product.name}</h4>
        <p>{product.price}€</p>
        <button class="p-2 bg-green-200 rounded-lg" on:click={() => addToCart(product)}>Ajouter au panier</button>
      </div>
    {/each}
  </div>

  <div class="cart-list p-5">
    {#each cart as item}
      {#if item.quantity > 0}
        <div class="cart-item mt-3">
          <img width="50" src={item.image} alt={item.name} />
          <div>
            {item.quantity}
            <button on:click={() => plusItem(item)}>+</button>
            <button on:click={() => minusItem(item)}>-</button>
          </div>
          <p>{item.price * item.quantity}€</p>
        </div>
      {/if}
    {/each}
    <div class="total">
      <h4>Total: {total}€</h4>
    </div>
  </div>
  <p>
    <button class="p-2 bg-green-200 rounded-lg" on:click={() => addToCart(product)}>Ajouter au panier</button>
  </p>

  <style>
    .product-list,
    .cart-item {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
    }

    .image {
      height: 150px;
      width: 150px;
      background-size: contain;
      background-position: center;
      background-repeat: no-repeat;
    }
    .total {
      text-align: right;
    }

    .cart-list {
      border: 2px solid;
      padding: 10px;
    }
  </style>
</div>
