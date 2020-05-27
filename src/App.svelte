<script>
  let count = 0;
  //functions to count items in cart
  function buttonAdd() {
    count += 1;
  }
  function buttonRemove() {
    count -= 1;
  }
  $: if (count <0 ) {
		alert(`Cart cannot have a negative number of items.`);
		count = 0;
	}
  //functions to open and close navigation side bar
  function openNav() {
    document.getElementById("mySidebar").style.width = "250px";
    document.getElementById("main").style.marginLeft = "250px";
  }

  function closeNav() {
    document.getElementById("mySidebar").style.width = "0";
    document.getElementById("main").style.marginLeft = "0";
  }
</script>

<style>
  /* style for store name */
  main {
    text-align: center;
    padding: 1em;
    max-width: 500px;
    margin: 0 auto;
  }
  h1 {
    color: #c300ff;
    text-transform: uppercase;
    font-size: 4em;
    font-weight: 200;
  }
  /* style for item name */
  h2 {
    color: #09010c;
    text-transform: uppercase;
    font-size: 2em;
    font-weight: 100;
  }
  /* style for item description */
  .desc {
    font-size: 1em;
  }
  /* style for outside container that has all the cards inside */
  .container {
    text-align: center;
  }
  /* style for item card */
  .card {
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
    max-width: 300px;
    margin-left: 30px;
    text-align: center;
    font-family: arial;
    display: inline-block;
  }
  /* style for item price */
  .price {
    color: grey;
    font-size: 22px;
  }
  .checked {
    color: orange;
  }

  /*style for card buttons */
  .card button {
    border: none;
    outline: 0;
    padding: 12px;
    color: white;
    background-color: #000;
    text-align: center;
    cursor: pointer;
    width: 100%;
    font-size: 18px;
  }
  .card button:hover {
    opacity: 0.7;
  }
  /* style for sidebar menu */
  .sidebar {
    height: 100%;
    width: 0;
    position: fixed;
    z-index: 1;
    top: 0;
    left: 0;
    background-color: rgb(46, 0, 42);
    overflow-x: hidden;
    transition: 0.5s;
    padding-top: 60px;
    float: right;
  }
  /* style for sidebar labels */
  .sidebar a {
    padding: 8px 8px 8px 32px;
    text-decoration: none;
    font-size: 25px;
    color: #ffffff;
    display: block;
    transition: 0.3s;
  }
  .sidebar a:hover {
    color: #ffadfb;
  }
  /* style for sidebar close button */
  .sidebar .closebtn {
    position: absolute;
    top: 0;
    right: 25px;
    font-size: 36px;
    margin-left: 50px;
  }
  /* style for sidebar open button */
  .openbtn {
    font-size: 20px;
    cursor: pointer;
    background-color: #111;
    color: white;
    padding: 5px 15px;
    border: none;
    float: center;
  }
  .openbtn:hover {
    background-color: #444;
  }
  /* style for cart button */
  .cart {
    font-size: 20px;
    cursor: pointer;
    background-color: #111;
    color: white;
    padding: 5px 15px;
    border: none;
    float: center;
  }
  /* sidebar transition */
  #mains {
    transition: margin-left 0.5s;
    padding: 16px;
  }
  /* resize sidebar for media */
  @media screen and (max-height: 450px) {
    .sidebar {
      padding-top: 15px;
    }
    .sidebar a {
      font-size: 18px;
    }
  }
</style>

<!-- Store Header, sidebar button, cart button-->
<main>
  <h1>Masha's Store</h1>
  <div id="mains">
    <button class="openbtn" on:click={openNav}>☰ Open Sidebar</button>
  </div>
  <button class="cart">Cart ({count})</button>

</main>
<!-- Sidebar-->
<div id="mySidebar" class="sidebar">
  <a href class="closebtn" on:click={closeNav}>×</a>
  <a href>Cart</a>
  <a href>Checkout</a>
  <a href>FAQ</a>
  <a href>Contact</a>
</div>
<!-- Apple card-->
<div class="container">
  <div class="card">
    <img
      src="https://i.ibb.co/yR6kmB0/unnamed-11.png"
      alt="apple"
      style="width:103.5%" />
    <h2>Red Apple</h2>
    <p class="price">$1.59</p>
    <link
      rel="stylesheet"
      href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css" />
    <span class="fa fa-star checked" />
    <span class="fa fa-star checked" />
    <span class="fa fa-star checked" />
    <span class="fa fa-star checked" />
    <span class="fa fa-star" />
    <p class="desc">Savor the sweet taste of Honeycrisp Apples.</p>
    <button type="button" on:click={buttonAdd} style="float:left;">
      Add to Cart
    </button>
    <button type="button" on:click={buttonRemove} style="float:left;">
      Remove from Cart
    </button>
  </div>
  <!-- Banana card-->
  <div class="card">
    <img
      src="https://lh3.googleusercontent.com/proxy/tHMVOK-wrOqiS7CFJot0zJdEVVBMHjcvjHVNEk7nExetQ0M-XYJoYTqWcFXylFWi_Lh_bNVhBZTKouMmIMyPaHOwNvr6JlG-wwz0H8UjLOMw4Csigt9ig_9DhGV3zPUdud3F4LQ"
      alt="banana"
      style="width:98%" />
    <h2>Banana</h2>
    <p class="price">$1.99</p>
    <span class="fa fa-star checked" />
    <span class="fa fa-star checked" />
    <span class="fa fa-star checked" />
    <span class="fa fa-star checked" />
    <span class="fa fa-star checked" />
    <p>
      Enhance breakfast and baking dishes by incorporating fresh Banana Fruit.
    </p>
    <button type="button" on:click={buttonAdd} style="float:left;">
      Add to Cart
    </button>
    <button type="button" on:click={buttonRemove} style="float:left;">
      Remove from Cart
    </button>
  </div>
  <!-- Orange card-->
  <div class="card">
    <img
      src="https://i.ibb.co/bLf0L43/788986-preview-preview.png"
      alt="orange"
      style="width:98%" />
    <h2>Orange</h2>
    <p class="price">$1.50</p>
    <span class="fa fa-star checked" />
    <span class="fa fa-star checked" />
    <span class="fa fa-star checked" />
    <span class="fa fa-star" />
    <span class="fa fa-star" />
    <p>
      Enjoy the fresh sweetness of Navel Oranges. A great source of vitamin C.
    </p>
    <button type="button" on:click={buttonAdd} style="float:left;">
      Add to Cart
    </button>
    <button type="button" on:click={buttonRemove} style="float:left;">
      Remove from Cart
    </button>
  </div>
  <!-- Kiwi card-->
  <div class="card">
    <img
      src="https://pluspng.com/img-png/kiwi-png-kiwi-png-image-fruit-kiwi-png-pictures-download-png-image-2464.png"
      alt="kiwi"
      style="width:95%" />
    <h2>Kiwi</h2>
    <p class="price">$1.39</p>
    <span class="fa fa-star checked" />
    <span class="fa fa-star checked" />
    <span class="fa fa-star" />
    <span class="fa fa-star" />
    <span class="fa fa-star" />
    <p>Treat yourself to the delicious and refreshing taste of kiwi.</p>
    <button type="button" on:click={buttonAdd} style="float:left;">
      Add to Cart
    </button>
    <button type="button" on:click={buttonRemove} style="float:left;">
      Remove from Cart
    </button>
  </div>
  <!-- Lime card-->
  <div class="card">
    <img
      src="https://lh3.googleusercontent.com/proxy/iveaEcYs0B-FTuBfxeR74EJv6bLMcPHI5xO6O8QXeHkUgWPIJKP3DS83Q7ryS2wQV227QBdYaF2ti0n79bL0VpXtLXnfhORFul5jIho2Beig47cHzxt7upsKuhwLPfhkvf1m"
      alt="lime"
      style="width:113.5%" />
    <h2>Lime</h2>
    <p class="price">$0.99</p>
    <span class="fa fa-star checked" />
    <span class="fa fa-star checked" />
    <span class="fa fa-star checked" />
    <span class="fa fa-star" />
    <span class="fa fa-star" />
    <p>
      Freshly squeezed limes provide a healthy dose of vitamin C to your diet.
    </p>
    <button type="button" on:click={buttonAdd} style="float:left;">
      Add to Cart
    </button>
    <button type="button" on:click={buttonRemove} style="float:left;">
      Remove from Cart
    </button>
  </div>
  <!-- Watermelon card-->
  <div class="card">
    <img
      src="https://i.ibb.co/yQxs02M/unnamed-12.png"
      alt="watermelon"
      style="width:88%" />
    <h2>Watermelon</h2>
    <p class="price">$2.99</p>
    <span class="fa fa-star checked" />
    <span class="fa fa-star checked" />
    <span class="fa fa-star checked" />
    <span class="fa fa-star checked" />
    <span class="fa fa-star" />
    <p>Watermelon is a good source of vitamin C, vitamin A, and potassium.</p>
    <button type="button" on:click={buttonAdd} style="float:left;">
      Add to Cart
    </button>
    <button type="button" on:click={buttonRemove} style="float:left;">
      Remove from Cart
    </button>
  </div>
  <!-- Strawberry card-->
  <div class="card">
    <img
      src="https://upload.wikimedia.org/wikipedia/commons/8/86/Strawberry_%28transparent_background%29.png"
      alt="strawberry"
      style="width:69.5%" />
    <h2>Strawberry</h2>
    <p class="price">$1.49</p>
    <span class="fa fa-star checked" />
    <span class="fa fa-star checked" />
    <span class="fa fa-star checked" />
    <span class="fa fa-star checked" />
    <span class="fa fa-star checked" />
    <p>
      The sweet, juicy flavor of Fresh Strawberries make them a delicious treat.
    </p>
    <button type="button" on:click={buttonAdd} style="float:left;">
      Add to Cart
    </button>
    <button type="button" on:click={buttonRemove} style="float:left;">
      Remove from Cart
    </button>
  </div>
  <!-- Blueberry card-->
  <div class="card">
    <img
      src="https://lh3.googleusercontent.com/proxy/8KLbL4nayQfpCdY6HEjxItn0nHKCv2ueh3l_k0jRfTwUBlOOkUYBY-sOH-rroVMtPl23l6t6TJ_cyeDS_9LwDHIwfTBR8Rvla8ygpI_InCdgAUrltDKvei9u"
      alt="blueberry"
      style="width:94%" />
    <h2>Bluberries</h2>
    <p class="price">$1.79</p>
    <span class="fa fa-star checked" />
    <span class="fa fa-star checked" />
    <span class="fa fa-star checked" />
    <span class="fa fa-star" />
    <span class="fa fa-star" />
    <p>
      From salads to muffins, these berries can help transform any ordinary
      food.
    </p>
    <button type="button" on:click={buttonAdd} style="float:left;">
      Add to Cart
    </button>
    <button type="button" on:click={buttonRemove} style="float:left;">
      Remove from Cart
    </button>
  </div>

</div>
