<!DOCTYPE html><html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Kombucha - Refrescos Artesanales</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f4;
        }
        header {
            background-color: #4CAF50;
            color: white;
            padding: 15px;
            text-align: center;
        }
        .container {
            width: 80%;
            margin: auto;
            overflow: hidden;
        }
        .products, .stores {
            display: flex;
            flex-wrap: wrap;
            justify-content: space-around;
            margin-top: 20px;
        }
        .product, .store {
            background: white;
            padding: 15px;
            margin: 10px;
            border-radius: 5px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            text-align: center;
            width: 30%;
        }
        footer {
            background-color: #333;
            color: white;
            text-align: center;
            padding: 10px;
            margin-top: 20px;
        }
        button {
            background-color: #4CAF50;
            color: white;
            border: none;
            padding: 10px;
            cursor: pointer;
            border-radius: 5px;
        }
        button:hover {
            background-color: #45a049;
        }
        .cart {
            text-align: center;
            margin-top: 20px;
        }
    </style>
    <script>
        let cart = [];function addToCart(product, price) {
        cart.push({ product, price });
        updateCart();
    }

    function updateCart() {
        let cartHTML = "<h2>Carrito de Compras</h2><ul>";
        let total = 0;
        cart.forEach(item => {
            cartHTML += <li>${item.product} - $${item.price}</li>;
            total += item.price;
        });
        cartHTML += </ul><h3>Total: $${total.toFixed(2)}</h3>;
        document.getElementById("cart").innerHTML = cartHTML;
    }

    function checkout() {
        alert("Redirigiendo a la pasarela de pago...");
    }
</script>

</head>
<body>
    <header>
        <h1>Kombucha - Refrescos Artesanales</h1>
    </header>
    <div class="container">
        <h2>Nuestros Productos</h2>
        <div class="products">
            <div class="product">
                <h3>Kombucha de Frutas</h3>
                <p>Refrescante y natural.</p>
                <p><strong>$50.00</strong></p>
                <button onclick="addToCart('Kombucha de Frutas', 50)">Agregar al Carrito</button>
            </div>
            <div class="product">
                <h3>Kombucha de Hierbas</h3>
                <p>Con ingredientes seleccionados.</p>
                <p><strong>$55.00</strong></p>
                <button onclick="addToCart('Kombucha de Hierbas', 55)">Agregar al Carrito</button>
            </div>
        </div>
        <div id="cart" class="cart">
            <h2>Carrito de Compras</h2>
            <p>Tu carrito está vacío.</p>
        </div>
        <button onclick="checkout()">Proceder al Pago</button>
        <h2>Puntos de Venta</h2>
        <div class="stores">
            <div class="store">
                <h3>Tienda Centro</h3>
                <p>Av. Principal #123</p>
            </div>
            <div class="store">
                <h3>Tienda Norte</h3>
                <p>Calle Secundaria #456</p>
            </div>
        </div>
    </div>
    <footer>
        <p>&copy; 2025 Kombucha - Todos los derechos reservados</p>
    </footer>
</body>
</html>
