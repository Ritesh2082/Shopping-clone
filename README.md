# Shopping-clone
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Online Shopping Clone</title>
    <style>
        body { font-family: Arial, sans-serif; margin: 0; padding: 0; }
        header { background: #333; color: white; padding: 15px; text-align: center; }
        .container { padding: 20px; }
        .product { border: 1px solid #ddd; padding: 15px; margin: 10px; display: inline-block; width: 200px; text-align: center; }
        .cart { background: #f4f4f4; padding: 10px; }
        button { background: #28a745; color: white; border: none; padding: 10px; cursor: pointer; }
    </style>
</head>
<body>
    <header>
        <h1>Online Shop</h1>
    </header>
    <div class="container">
        <div class="product">
            <h3>Product 1</h3>
            <p>$10.00</p>
            <button onclick="addToCart('Product 1', 10.00)">Add to Cart</button>
        </div>
        <div class="product">
            <h3>Product 2</h3>
            <p>$15.00</p>
            <button onclick="addToCart('Product 2', 15.00)">Add to Cart</button>
        </div>
    </div>
    <div class="cart">
        <h2>Shopping Cart</h2>
        <ul id="cart-list"></ul>
    </div>
    <script>
        let cart = [];
        function addToCart(product, price) {
            cart.push({ product, price });
            updateCart();
        }
        function updateCart() {
            let cartList = document.getElementById("cart-list");
            cartList.innerHTML = "";
            cart.forEach(item => {
                let li = document.createElement("li");
                li.innerText = `${item.product} - $${item.price.toFixed(2)}`;
                cartList.appendChild(li);
            });
        }
    </script>
</body>
</html>
