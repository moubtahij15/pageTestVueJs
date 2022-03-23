<script>
 window.addEventListener("scroll", function(){
   const header = document.querySelector("header");
    header.classList.toggle("sticky", window.scrollY>0);
})

function toggleMenu(){
  const menuToggle = document.querySelector(".menuToggle");
    const navigation = document.querySelector(".navigation");
    menuToggle.classList.toggle("active");
    navigation.classList.toggle("active");
}

// VueJS Script
  export default {
    data() {
      return {
        message: 'Just a long long long paragraph to test with!'
      }
    },
    methods: {
      reverseMessage() {
        this.message = this.message.split('').reverse().join('')
      },
      notify() {
        alert('navigation was prevented.')
      }
    }
  }
// VueJS Script
</script>

<template>
  <header>
      <a href="#" class="logo">Tesing<span>Page</span></a>
      <div class="menuToggle" onclick="toggleMenu()"></div>
      <ul class="navigation">
        <li><a href="#" onclick="toggleMenu()">Home</a></li>
        <li><a href="#" onclick="toggleMenu()">About</a></li>
        <li><a href="#" onclick="toggleMenu()">Option 1</a></li>
        <li><a href="#" onclick="toggleMenu()">Option 2</a></li>
        <li><a href="#" onclick="toggleMenu()">Option 3</a></li>
        <li id="listbreak">|</li>
        <li><a href="#" onclick="toggleMenu()">Signin</a></li>
      </ul>
  </header>
  <section class="banner" id="banner">
    <div class="dimlight"></div>
      <div class="content">
      <!-- VueJS Template -->

        <h1 style="color: white">{{ message }}</h1>

        <button @click="reverseMessage">Reverse Message</button>

        <button @click="message += '!'">Append "!"</button>
        
        <a href="https://vuejs.org" @click.prevent="notify"></a>

      <!-- VueJS Template -->
      </div>
  </section>
</template>

<style>

/* VueJs Styles */

  button, a {
    display: block;
    margin-bottom: 1em;
  }

/* VueJs Styles */

*{
    font-family: "Poppins", sans-serif;
    padding: 0;
    margin: 0;
    box-sizing: border-box;
    scroll-behavior: smooth;
}

header
{
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    padding: 40px 100px;
    z-index: 100;
    display: flex;
    justify-content: space-between;
    align-items: center;
    transition: 0.5s;
}

header.sticky
{
    background: #fff;
    padding: 10px 100px;
    box-shadow: 0 5px 20px rgba(0,0,0,0.05);
}

header .logo
{
    color: #fff;
    font-weight: 700;
    font-size: 2em;
    text-decoration: none;
}

header.sticky .logo
{
    color: #111;
}

header .logo span
{
    color: #ff114d
}

header .navigation
{
    position: relative;
    display: flex;
}

header .navigation li
{
    list-style: none;
    margin-left: 30px;
}

header .navigation li a 
{
    text-decoration: none;
    color: #fff;
    font-weight: 300;
}

header.sticky .navigation li a
{
    color: #111;
}

header .navigation li a:hover
{
    color: #ff114d;
}

#listbreak
{
    color:white;
}

header.sticky #listbreak
{
    color:black;
}


section
{
    padding: 100px;
}

.banner
{
    position: relative;
    width: 100%;
    min-height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: black;
    background-size: cover;
}

.dimlight
{
    position: absolute;
    background-color: rgba(0, 0, 0, 0.5);
    width: 100%;
    height: 100%;
}


.banner .content
{
    max-width: 900px;
    text-align: center;
    z-index: 1;
}

.banner .content h2
{
    font-size: 5em;
    color: #fff;
}

.banner .content p
{
    font-size: 1em;
    color: #fff; 
}

</style>
