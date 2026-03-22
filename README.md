<!DOCTYPE html>
<head>
  <me charset="UTF-8" />
  <me name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Donut Lovers</title>

  <style>
    section { display: none; }
    section.active { display: block; }
  </style>
</head>

<body>

<body>

<header>
  <h1>🍩 Donut Lovers</h1>
  <nav>
    <button onclick="showPage('home')">Home</button>
    <button onclick="showPage('donuts')">Donuts</button>
    <button onclick="showPage('tips')">Tips & Guides</button>
    <button onclick="showPage('contact')">Contact</button>
  </nav>
</header>

<main>
  <section id="home">
    <h2>Home</h2>
    <h3>Welcome to Donut Lovers! 🍩</h3>
    <p><strong>Your sweet journey starts here!</strong></p>
    <p>Explore different kinds of donuts from around the world.</p>
  </section>

  <section id="donuts" style="display:none;">
    <h2>Donuts</h2>
    <h3>Select Your Flavor:</h3>
    <label><input type="checkbox"> Sweet</label>
    <label><input type="checkbox"> Chocolate</label>
    <label><input type="checkbox"> Matcha</label>

    <h3>Choose Donut Type:</h3>
    <select id="donutType">
      <option value="all">All</option>
      <option value="classic">Classic</option>
      <option value="filled">Filled</option>
      <option value="gourmet">Gourmet</option>
    </select>

    <div>
   <article class="donut-card classic sweet">
  <h4>Glazed Donut</h4>
  <p>Sweet, simple, and timeless.</p>
  <p><strong>₱25</strong></p>
  <button onclick="orderDonut('Glazed Donut', 25)">Order</button>
  </article>

    <article class="donut-card filled chocolate">
  <h4>Chocolate Filled</h4>
  <p>Soft donut with rich chocolate inside.</p>
  <p><strong>₱35</strong></p>
  <button onclick="orderDonut('Chocolate Filled', 35)">Order</button>
    </article>

   <article class="donut-card gourmet matcha">
  <h4>Matcha Donut</h4>
  <p>Unique green tea flavor.</p>
  <p><strong>₱45</strong></p>
  <button onclick="orderDonut('Matcha Donut', 45)">Order</button>
  </article>
    </div>

    <button type="button" onclick="filterDonuts()">Apply Filter</button>
  </section>

  <section id="tips" style="display:none;">
    <h2>Tips & Guides</h2>
    <h3>🍩 Donut Storage Tips</h3>
    <ul>
      <li>Keep donuts in a cool, dry place.</li>
      <li>Store in airtight containers.</li>
      <li>Avoid refrigeration if possible.</li>
    </ul>
  </section>

  <section id="contact" style="display:none;">
    <h2>Contact</h2>
    <h3>📞 Get in Touch</h3>
    <p><strong>Facebook:</strong><br>
      <a href="https://www.facebook.com/christianking.requintaii" target="_blank" rel="noopener">Visit my Facebook Profile</a>
    </p>
    <p><strong>Email:</strong><br>
      <a href="kingsrequinta@gmail.com">kingsrequinta@gmail.com</a>
    </p>

    <h3>Or send a message:</h3>
    <form>
      <label for="name">Name:</label><br>
      <input id="name" type="text"><br><br>

      <label for="email">Email:</label><br>
      <input id="email" type="email"><br><br>

      <button type="submit">Submit</button>
    </form>
  </section>
</main>

<script>
function showPage(pageId) {
  document.querySelectorAll('main section').forEach(sec => sec.style.display = "none");
  document.getElementById(pageId).style.display = "block";
}

function orderDonut(name, price) {
  alert("You selected: " + name + " 🍩\nPrice: ₱" + price);
}

function filterDonuts() {
  const type = document.getElementById("donutType").value;
  document.querySelectorAll(".donut-card").forEach(donut => {
    donut.style.display = (type === "all" || donut.classList.contains(type)) ? "block" : "none";
  });
}
</script>

</body>
</html>
