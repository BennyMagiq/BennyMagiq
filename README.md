<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Clothing Design Website</title>
    <style>
        /* Add your CSS styles for the website layout and design here */
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f4;
        }

        header {
            background-color: #333;
            color: white;
            padding: 10px;
            text-align: center;
        }

        /* Add more styles for other sections as needed */
    </style>
</head>
<body>
    <header>
        <h1>Clothing Design</h1>
    </header>

    <section id="products">
        <!-- Product listing goes here -->
        <div class="product">
            <img src="product1.jpg" alt="Product 1">
            <h2>Product 1</h2>
            <p>Description of Product 1.</p>
            <p>$25.00</p>
            <button onclick="addToCart(1)">Add to Cart</button>
        </div>

        <div class="product">
            <img src="product2.jpg" alt="Product 2">
            <h2>Product 2</h2>
            <p>Description of Product 2.</p>
            <p>$30.00</p>
            <button onclick="addToCart(2)">Add to Cart</button>
        </div>

        <!-- Add more products as needed -->
    </section>

    <section id="cart">
        <h2>Shopping Cart</h2>
        <ul id="cart-items">
            <!-- Cart items will be dynamically added here using JavaScript -->
        </ul>
        <p>Total: $<span id="cart-total">0.00</span></p>
        <button onclick="checkout()">Checkout</button>
    </section>

    <script>
        // Add your JavaScript code for interactivity here
        let cart = [];

        function addToCart(productId) {
            // Implement logic to add product to cart
            // You can fetch product details from a server or use hardcoded values
            let product = {
                id: productId,
                name: `Product ${productId}`,
                price: productId === 1 ? 25.00 : 30.00,
            };

            cart.push(product);
            updateCart();
        }

        function updateCart() {
            // Update the cart display
            let cartItemsElement = document.getElementById('cart-items');
            let cartTotalElement = document.getElementById('cart-total');
            cartItemsElement.innerHTML = '';

            let total = 0;

            cart.forEach(item => {
                let listItem = document.createElement('li');
                listItem.textContent = `${item.name} - $${item.price.toFixed(2)}`;
                cartItemsElement.appendChild(listItem);
                total += item.price;
            });

            cartTotalElement.textContent = total.toFixed(2);
        }

        function checkout() {
            // Implement checkout logic (e.g., send cart data to server for processing)
            alert('Checkout functionality not implemented in this example.');
        }
    </script>
</body>
</html>
