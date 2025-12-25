# Ex.07 Restaurant Website
# Date:
# AIM:
To develop a static Restaurant website to display the food items and services provided by them.

# DESIGN STEPS:
## Step 1:
Requirement collection.

## Step 2:
Creating the layout using HTML and CSS.

## Step 3:
Updating the sample content.

## Step 4:
Choose the appropriate style and color scheme.

## Step 5:
Validate the layout in various browsers.

## Step 6:
Validate the HTML code.

## Step 7:
Publish the website in the given URL.

# PROGRAM:
```
res.html

<!DOCTYPE html>
{% load static %}
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>MOONBUCKS</title>

<style>
    * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
    }

    body {
        font-family: serif;
        background: #0d0d0d ;
        color: #f0e7d5;
    }

    /* ================= NAVBAR ================= */
    nav {
        width: 100%;
        padding: 15px 5%;
        background: #ffffff;
        border-bottom: 1px solid #ddd;
        display: flex;
        justify-content: space-between;
        align-items: center;
        position: sticky;
        top: 0;
        z-index: 1000;
    }

    nav .logo {
        font-size: 2rem;
        color: #0d0d0d;
    }

    nav ul {
        display: flex;
        gap: 30px;
        list-style: none;
        color: #0d0d0d;
    }

    nav li {
        font-size: 1.2rem;
        cursor: pointer;
    }

    /* Mobile menu stacking */
    @media (max-width: 700px) {
        nav ul {
            gap: 15px;
        }
        nav li {
            font-size: 0.9rem;
        }
        nav .logo {
        font-size: 1.7rem;
    }
    }

    /* ================= HERO SECTION ================= */
    .hero {
        width: 100%;
        padding: 60px 5%;
        display: flex;
        align-items: center;
        justify-content: space-between;
        flex-wrap: wrap;
    }

    .hero-text {
        flex: 1 1 400px;
    }

    .hero-text h1 {
        font-size: clamp(40px, 6vw, 80px);
        margin-bottom: 20px;
    }

    .hero-text p {
        font-size: clamp(20px, 3vw, 30px);
    }

    .hero-image {
        flex: 1 1 350px;
        display: flex;
        justify-content: center;
        padding: 20px;
    }

    .hero-image img {
        width: 100%;
        max-width: 450px;
    }

    /* ================= FEATURES / MENU GRID ================= */
    .grid-section {
        padding: 60px 5%;
    }

    .grid-title {
        font-size: clamp(30px, 5vw, 50px);
        margin-bottom: 30px;
        text-align: center;
    }

    .grid {
        display: grid;
        gap: 25px;
        grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    }

    .grid-item {
        background: #fff;
        padding: 25px;
        border-radius: 20px;
        box-shadow: 0px 0px 10px rgba(0,0,0,0.1);
        text-align: center;
        color: #0d0d0d;
    }

    .grid-item img {
        width: 100%;
        border-radius: 15px;
        margin-bottom: 15px;
    }

    /* ================= FOOTER ================= */
    footer {
        text-align: center;
        padding: 20px 0;
        background: #cec0b3;
        color: #0d0d0d;
        margin-top: 40px;
    }
</style>
</head>
<body>

<!-- NAVBAR -->
<nav>
    <div class="logo">MOONBUCKS</div>
    <ul>
        <li onclick="window.location.href='res.html'">Home</li>
        <li onclick="window.location.href='order.html'">Products</li>
        <li onclick="window.location.href='about.html'">About</li>
        <li onclick="window.location.href='contact.html'">Contact</li>
    </ul>
</nav>

<!-- HERO SECTION -->
<section class="hero">
    <div class="hero-text">
        <h1>Welcome to MOONBUCKS</h1>
        <p>The place with the best drinks in the world</p>
    </div>

    <div class="hero-image">
        <img id="item" src="headphone.png" alt="">
    </div>
</section>

<!-- GRID SECTION -->
<section class="grid-section">
    <h2 class="grid-title">New Arrivals</h2>

    <div class="grid">
        <div class="grid-item">
        <img src="{% static 'galaxy delight.png' %}">
        <h3>Galaxy Delight</h3>
        <p>₹700</p>
    </div>

    <div class="grid-item" >
        <img src="{% static 'starwberry delight.png' %}">
        <h3>Strawberry Delight</h3>
        <p>₹600</p>
    </div>

    <div class="grid-item">
        <img src="{% static 'blueberry delight.png' %}">
        <h3>Blueberry Delight</h3>
        <p>₹800</p>
    </div>

    <div class="grid-item" >
        <img src="{% static 'oreo delight.png' %}">
        <h3>Oreo Delight</h3>
        <p>₹1000</p>
    </div>

    </div>
</section>

<!-- FOOTER -->
<footer>
    © 2025 MOONBUCKS. All rights reserved.
</footer>
<script>
    function openOrder(id) {
    window.location.href = "order.html?id=" + id;
}
    const ibox =[
        {item:"{% static 'galaxy delight.png' %}"},
        {item:"{% static 'blueberry delight.png' %}"},
        {item:"{% static 'oreo delight.png' %}"}
    ]
    let o=0

    setInterval(() => {
    o = (o + 1) % ibox.length;
    document.getElementById("item").src = ibox[o].item;
}, 2000);


</script>
</body>
</html>


contact.html

<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>TECHY</title>
<style>
    * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
    }

    body {
        font-family:  serif;
        background: #0d0d0d ;
        color: #f0e7d5;
        min-height: 100vh;
    display: flex;
    flex-direction: column;
    }
    
 /* ================= NAVBAR ================= */
    nav {
        width: 100%;
        padding: 15px 5%;
        background: #ffffff;
        border-bottom: 1px solid #ddd;
        display: flex;
        justify-content: space-between;
        align-items: center;
        position: sticky;
        top: 0;
        z-index: 1000;
    }

    nav .logo {
        font-size: 2rem;
        color: #0d0d0d;
    }

    nav ul {
        display: flex;
        gap: 30px;
        list-style: none;
        color: #0d0d0d;
    }

    nav li {
        font-size: 1.2rem;
        cursor: pointer;
    }

    /* Mobile menu stacking */
    @media (max-width: 700px) {
        nav ul {
            gap: 15px;
        }
        nav li {
            font-size: 0.9rem;
        }
        nav .logo {
        font-size: 1.7rem;
    }
    }
footer {
        text-align: center;
        padding: 20px 0;
        background: #cec0b3;
        color: #0d0d0d;
        margin-top: 40px;
    }

    .grid-section {
        padding: 60px 5%;
        flex:1;
    }

    .grid-title {
        font-size: clamp(30px, 5vw, 50px);
        margin-bottom: 30px;
        text-align: center;
    }

    .grid {
        font-size: clamp(5px, 3vw, 20px);
        margin-bottom: 30px;
        text-align: center;
    }
</style>
</head>
<body>
<nav>
    <div class="logo">TECHY</div>
    <ul>
        <li onclick="window.location.href='res.html'">Home</li>
        <li onclick="window.location.href='order.html'">Products</li>
        <li onclick="window.location.href='about.html'">About</li>
        <li onclick="window.location.href='contact.html'">Contact</li>
    </ul>
</nav>
<section class="grid-section">
    <h2 class="grid-title">Contact us through!</h2>

    <div class="grid">
        <h1>insta: @moonbucks.2025<br>email:  moonbucks2025@gmail.com<br>whatsapp:  044  1234-5678</h1>
    </div>
</section>
<footer>
    © 2025 MOONBUCKS. All rights reserved.
</footer>
</body>
</html>


about.html

<!DOCTYPE html>
{% load static %}
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>MOONBUCKS</title>
<style>
    * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
    }

    body {
        font-family: 'CosmicSerif', serif;
        background: #0d0d0d ;
        color: #f0e7d5;
        min-height: 100vh;
    display: flex;
    flex-direction: column;
    }
 /* ================= NAVBAR ================= */
    nav {
        width: 100%;
        padding: 15px 5%;
        background: #ffffff;
        border-bottom: 1px solid #ddd;
        display: flex;
        justify-content: space-between;
        align-items: center;
        position: sticky;
        top: 0;
        z-index: 1000;
    }

    nav .logo {
        font-size: 2rem;
        color: #0d0d0d;
    }

    nav ul {
        display: flex;
        gap: 30px;
        list-style: none;
        color: #0d0d0d;
    }

    nav li {
        font-size: 1.2rem;
        cursor: pointer;
    }

    /* Mobile menu stacking */
    @media (max-width: 700px) {
        nav ul {
            gap: 15px;
        }
        nav li {
            font-size: 0.9rem;
        }
        nav .logo {
        font-size: 1.7rem;
    }
    }
     .hero {
        width: 100%;
        padding: 60px 5%;
        display: flex;
        align-items: center;
        justify-content: space-between;
        flex-wrap: wrap;
    }

    .hero-text {
        flex: 1 1 400px;
    }

    .hero-text h1 {
        font-size: clamp(40px, 6vw, 80px);
        margin-bottom: 20px;
    }

    .hero-text p {
        font-size: clamp(20px, 3vw, 30px);
    }

    .hero-image {
        flex: 1 1 350px;
        display: flex;
        justify-content: center;
        padding: 20px;
    }

    .hero-image img {
        width: 100%;
        max-width: 450px;
    }

    footer {
        text-align: center;
        padding: 20px 0;
        background: #cec0b3;
        color: #0d0d0d;
        margin-top: 40px;
    }
    .grid-section {
        padding: 60px 5%;
        flex:1;
    }

    .grid-title {
        font-size: clamp(30px, 5vw, 50px);
        margin-bottom: 30px;
        text-align: center;
    }

    .grid {
        font-size: clamp(5px, 3vw, 20px);
        margin-bottom: 30px;
        text-align: center;
    }
</style>
</head>
<body>

<!-- NAVBAR -->
<nav>
    <div class="logo">MOONBUCKS</div>
    <ul>
        <li onclick="window.location.href='res.html'">Home</li>
        <li onclick="window.location.href='order.html'">Products</li>
        <li onclick="window.location.href='about.html'">About</li>
        <li onclick="window.location.href='contact.html'">Contact</li>
    </ul>
</nav>
<section class="hero">
    <div class="hero-text">
        <h1>About MOONBUCKS</h1>
        <p>Where you get Preminum drinks</p>
    </div>

    <div class="hero-image">
        <img id="item" src="{% static 'galaxy delight.png' %}" alt="">
    </div>
</section>
<section class="hero">
    

    <div class="hero-image">
        <img id="item" src="{% static 'oreo delight.png' %}" alt="">
    </div>
    <div class="hero-text">
        <h1>Who We Are</h1>
        <p>MOONBUCKS is a premium coffee shop that offers a unique and delightful experience for coffee lovers. We are committed to providing the highest quality drinks and exceptional service.</p>
    </div>
</section>
<section class="hero">
    <div class="hero-text">
        <h1>Our Mission</h1>
        <p>Our mission is to bring premium, reliable tech to everyone — without complicated shopping or overpriced products.</p>
    </div>

    <div class="hero-image">
        <img id="item" src="{% static 'starwberry delight.png' %}" alt="">
    </div>
</section>
<section class="hero">
    

    <div class="hero-image">
        <img id="item" src="{% static 'oreo delight.png' %}" alt="">
    </div>
    <div class="hero-text">
        <h1>What We Offer</h1>
        <p>extraodinary looks
<br>High quality drinks
<br>Preminum coustomer service
<br>Honest reviews </p>
    </div>
</section>
<footer>
    © 2025 MOONBUCKS. All rights reserved.
</footer>
</body>
</html>


order.html

<!DOCTYPE html>
{% load static %}
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>MOONBUCKS</title>
<style>
    * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
    }

    body {
        font-family: 'CosmicSerif', serif;
        background: #0d0d0d ;
        color: #f0e7d5;
    }
 /* ================= NAVBAR ================= */
    nav {
        width: 100%;
        padding: 15px 5%;
        background: #ffffff;
        border-bottom: 1px solid #ddd;
        display: flex;
        justify-content: space-between;
        align-items: center;
        position: sticky;
        top: 0;
        z-index: 1000;
    }

    nav .logo {
        font-size: 2rem;
        color: #0d0d0d;
    }

    nav ul {
        display: flex;
        gap: 30px;
        list-style: none;
        color: #0d0d0d;
    }

    nav li {
        font-size: 1.2rem;
        cursor: pointer;
    }

    /* Mobile menu stacking */
    @media (max-width: 700px) {
        nav ul {
            gap: 15px;
        }
        nav li {
            font-size: 0.9rem;
        }
        nav .logo {
        font-size: 1.7rem;
    }
    }
    /* ================= FEATURES / MENU GRID ================= */
    .grid-section {
        padding: 60px 5%;
    }

    .grid-title {
        font-size: clamp(30px, 5vw, 50px);
        margin-bottom: 30px;
        text-align: center;
    }

    .grid {
        display: grid;
        gap: 25px;
        grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    }

    .grid-item {
        background: #fff;
        padding: 25px;
        border-radius: 20px;
        box-shadow: 0px 0px 10px rgba(0,0,0,0.1);
        text-align: center;
        color: #0d0d0d;
    }

    .grid-item img {
        width: 100%;
        border-radius: 15px;
        margin-bottom: 15px;
    }

    /* ================= FOOTER ================= */
    footer {
        text-align: center;
        padding: 20px 0;
        background: #cec0b3;
        color: #0d0d0d;
        margin-top: 40px;
    }
</style>
</head>
<body>

<!-- NAVBAR -->
<nav>
    <div class="logo">MOONBUCKS</div>
    <ul>
        <li onclick="window.location.href='res.html'">Home</li>
        <li onclick="window.location.href='order.html'">Products</li>
        <li onclick="window.location.href='about.html'">About</li>
        <li onclick="window.location.href='contact.html'">Contact</li>
    </ul>
</nav>
<section class="grid-section">
    <h2 class="grid-title">Our Products</h2>

    <div class="grid">

    <div class="grid-item" >
        <img src="{% static 'galaxy delight.png' %}">
        <h3>Galaxy delight</h3>
        <p>₹700</p>
    </div>

    <div class="grid-item">
        <img src="{% static 'starwberry delight.png' %}">
        <h3>Strawberry delight</h3>
        <p>₹600</p>
    </div>

    <div class="grid-item">
        <img src="{% static 'oreo delight.png' %}">
        <h3>Oreo delight </h3>
        <p>₹1000</p>
    </div>

    <div class="grid-item">
        <img src="{% static 'blueberry delight.png' %}">
        <h3>Blueberry delight</h3>
        <p>₹800</p>
    </div>

    <div class="grid-item">
        <img src="{% static 'raspberry delight.png' %}">
        <h3>Raspberry delight</h3>
        <p>₹800</p>
    </div>

    <div class="grid-item" >
        <img src="{% static 'cold.png' %}">
        <h3>Cold coffee</h3>
        <p>₹600</p>
    </div>

    <div class="grid-item">
        <img src="{% static 'iced macha.png' %}">
        <h3>Iced Macha</h3>
        <p>₹1000</p>
    </div>

    <div class="grid-item" >
        <img src="{% static 'chocothickshake.png' %}">
        <h3>Chocolate Thickshake</h3>
        <p>₹1200</p>
    </div>

    <div class="grid-item">
        <img src="{% static 'Strawberry thick.png' %}">
        <h3>Strawberry Thickshake</h3>
        <p>₹1000</p>
    </div>

    <div class="grid-item" >
        <img src="{% static 'vanilla choco.png' %}">
        <h3>Vanilla Chocolate Shake</h3>
        <p>₹1200</p>
    </div>

    <div class="grid-item" >
        <img src="{% static 'mix.png' %}">
        <h3>Mixberry Thickshake</h3>
        <p>₹1500</p>
    </div>

    <div class="grid-item" >
        <img src="{% static 'mango.png' %}">
        <h3>Mango Thickshake</h3>
        <p>₹1000</p>
    </div>

</div>

</section>
<footer>
    © 2025 MOONBUCKS. All rights reserved.
</footer>
</body>
</html>

```
# OUTPUT:
<img width="1879" height="1079" alt="528994628-a62ea3ed-1980-4a19-995b-ed99550ef61d" src="https://github.com/user-attachments/assets/21bfc164-bdca-4f4c-97dc-ce61370ed8b2" />
<img width="1894" height="1079" alt="528994669-e5918746-3ce6-44dc-b31f-c6532c47dc41" src="https://github.com/user-attachments/assets/6f12082f-9f2c-4599-945c-a9f7001714a3" />
<img width="1919" height="1079" alt="528995070-370179ce-44c8-48bd-814f-8ebf6777fddb" src="https://github.com/user-attachments/assets/b8f6da7c-1879-48c7-bb97-b2fc7b1afc3b" />
<img width="1919" height="1079" alt="528995097-2ac849ad-3f91-49bf-8540-aa84600709cc" src="https://github.com/user-attachments/assets/cc501b19-305b-4ecc-a029-e8bcda682262" />
<img width="1919" height="1079" alt="528995097-2ac849ad-3f91-49bf-8540-aa84600709cc" src="https://github.com/user-attachments/assets/d699932e-b222-422c-bbf5-979f110a1f9b" />
<img width="1919" height="1079" alt="528995139-a05003fb-ac97-4def-a4ac-a69f0e51298f" src="https://github.com/user-attachments/assets/16609b68-252b-4b0d-b639-373203aa9406" />
<img width="1919" height="1079" alt="528995188-a25a9663-9353-4f98-a285-be27729ea7e5" src="https://github.com/user-attachments/assets/fbf12f77-5cbc-44da-a3d5-6bad88a4cee6" />
<img width="1919" height="1079" alt="528995230-7473c6a9-01f5-414c-80c3-a6ed3e6c5d0b" src="https://github.com/user-attachments/assets/2ab8d648-9591-447e-91b8-6f84b0ed76a8" />

# RESULT:
The program for designing software company website using HTML and CSS is completed successfully.
