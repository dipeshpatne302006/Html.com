# Html.com
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Simple E-commerce Example</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            margin: 0;
            padding: 20px;
            background-color: #f4f4f4;
        }

        h1 {
            color: #333;
        }

        #product-list {
            display: flex;
            gap: 20px;
            margin-top: 20px;
        }

        .product {
            background-color: #fff;
            padding: 15px;
            border-radius: 8px;
            box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
            text-align: center;
        }

        button {
            background-color: #4caf50;
            color: #fff;
            padding: 10px 15px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
        }

        #shopping-cart {
            margin-top: 20px;
            background-color: #fff;
            padding: 15px;
            border-radius: 8px;
            box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
        }

        #cart-items {
            list-style-type: none;
            padding: 0;
        }

        li {
            margin-bottom: 5px;
        }

        p {
            margin: 10px 0 0;
        }
    </style>
</head>
<body>

<!-- Your existing HTML code here -->
<h1>Welcome to Our Online Store</h1>

<div id="product-list">
    <!-- Product 1 -->
    <div class="product">
        <h2>Product 1</h2>
        <p>Price: $19.99</p>
        <button onclick="addToCart('Product 1', 19.99)">Add to Cart</button>
    </div>

    <!-- Product 2 -->
    <div class="product">
        <h2>Product 2</h2>
        <p>Price: $29.99</p>
        <button onclick="addToCart('Product 2', 29.99)">Add to Cart</button>
    </div>

    <!-- Add more products as needed -->
</div>

<div id="shopping-cart">
    <h2>Shopping Cart</h2>
    <ul id="cart-items"></ul>
    <p>Total: $<span id="cart-total">0.00</span></p>
</div>

<script>
    let cart = [];
    let total = 0;

    function addToCart(product, price) {
        cart.push({ product, price });
        total += price;

        updateCart();
    }

    function updateCart() {
        const cartItems = document.getElementById('cart-items');
        const cartTotal = document.getElementById('cart-total');

        // Clear existing items
        cartItems.innerHTML = '';

        // Populate cart items
        cart.forEach(item => {
            const li = document.createElement('li');
            li.textContent = `${item.product} - $${item.price.toFixed(2)}`;
            cartItems.appendChild(li);
        });

        // Update total
        cartTotal.textContent = total.toFixed(2);
    }
</script>

</body>
</html>
