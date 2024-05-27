<template>
  <div id="app">
    <header>
      <nav>
        <div class="logo">
          <img src="" alt="Dani Clothing">
        </div>
        <ul>
          <li><a href="#">Beranda</a></li>
          <li><a href="#">Produk</a></li>
          <li><a href="#">Kategori</a></li>
          <li><a href="#">Tentang</a></li>
          <li><a href="#">Kontak</a></li>
        </ul>
        <div class="auth">
          <button>Login</button>
          <button>Register</button>
        </div>
      </nav>
    </header>
    </div>

  <div class="q-pa-md">
    <q-carousel
      animated
      v-model="slide"
      navigation
      infinite
      :autoplay="autoplay"
      arrows
      transition-prev="slide-right"
      transition-next="slide-left"
      @mouseenter="autoplay = false"
      @mouseleave="autoplay = true"
    >
      <q-carousel-slide name="1" img-src="https://cdn.quasar.dev/img/mountains.jpg" />
      <q-carousel-slide name="2" img-src="https://cdn.quasar.dev/img/parallax1.jpg" />
      <q-carousel-slide name="3" img-src="https://cdn.quasar.dev/img/parallax2.jpg" />
      <q-carousel-slide name="4" img-src="https://cdn.quasar.dev/img/quasar.jpg" />
    </q-carousel>
  </div>
  
    <main>
      <section class="hero">
        <div class="hero-content">
          <h1>Koleksi Baju Terbaru</h1>
          <p>Dapatkan penawaran terbaik untuk koleksi baju terbaru kami</p>
          <button class="cta">Belanja Sekarang</button>
        </div>
        <img src="/images/gambar 9.jpeg"
         alt="Koleksi Baju Terbaru">
      </section>

      <section class="categories">
        <h2>Kategori Produk</h2>
        <div class="category-list">
          <div class="category-item" v-for="category in categories" :key="category.id">
            <img :src="category.image" :alt="category.name">
            <h3>{{ category.name }}</h3>
          </div>
        </div>
      </section>

      <section class="featured-products">
        <h2>Produk Terlaris</h2>
        <div class="product-list">
          <div class="product-item" v-for="product in featuredProducts" :key="product.id">
            <img :src="product.image" :alt="product.name">
            <h3>{{ product.name }}</h3>
            <p class="price">{{ product.price }}</p>
            <button class="buy-btn">Beli</button>
          </div>
        </div>
      </section>
    </main>

    <div class="q-pa-md">
    <q-card class="my-card">
      <iframe width="300" height="315" src="https://www.youtube.com/embed/YVJj-INq5nk?si=IL9np1dk7NBxh354" frameborder="0" allowfullscreen></iframe>





      <q-card-section>
        <div class="text-h6">Agak Laen</div>
        <div class="text-subtitle2">by Dani</div>
      </q-card-section>

      <q-card-section class="q-pt-none">
        Semoga dengan lagu agak laen bisa menolong nilai saya yang agak laen hehe.
      </q-card-section>
    </q-card>
    
    <footer>
      <div class="footer-content">
        <div class="about">
          <h3>Tentang Toko Kami</h3>
          <p>{{ about }}</p>
    </div>
      </div>
      <p class="copyright">&copy; {{ currentYear }} Dani Clothing. All rights reserved.</p>
    </footer>
  </div>
</template>

<script>
import { ref } from 'vue'

export default {
  name: 'App',
  setup() {
    const slide = ref(1);
    const autoplay = ref(true);

    return {
      slide,
      autoplay,
      categories: [
        { id: 1, name: 'Baju Wanita', image: './images/gambar 4.jpeg' },
        { id: 2, name: 'Baju Pria', image: './images/gambar 3.jpeg' },
        { id: 3, name: 'Baju Anak', image: './images/gambar 2.jpeg' },
        { id: 4, name: 'Baju Olahraga', image: './images/gambar 1.jpeg' }
      ],
      featuredProducts: [
        { id: 1, name: 'Baju Wanita Terbaru', price: 'Rp 99.000', image: './images/gambar 8.jpeg' },
        { id: 2, name: 'Kemeja Pria Keren', price: 'Rp 149.000', image: './images/gambar 5.jpeg' },
        { id: 3, name: 'Dress Anak Lucu', price: 'Rp 79.000', image: './images/gambar 7.jpeg' },
        { id: 4, name: 'Jaket Olahraga', price: 'Rp 199.000', image: './images/gambar 6.jpeg' }
      ],
      testimonials: [
        { id: 1, name: 'John Doe', review: 'Pelayanan toko ini sangat memuaskan!', image: 'testimonial1.jpg' },
        { id: 2, name: 'Jane Smith', review: 'Produk yang dijual berkualitas tinggi.', image: 'testimonial2.jpg' },
        { id: 3, name: 'Bob Johnson', review: 'Saya sangat senang berbelanja di sini.', image: 'testimonial3.jpg' }
      ],
      about: 'Dani Clothing adalah toko online yang menyediakan berbagai macam baju berkualitas dengan harga terjangkau. Kami berkomitmen untuk memberikan pelayanan terbaik bagi pelanggan kami.',
      currentYear: new Date().getFullYear()
    };
  }
}
</script>


<style>
/* Global Styles */
body {
  font-family: 'Poppins', sans-serif;
  margin: 0;
  padding: 0;
  background-color: #f8f9fa;
  color: #333;
}

/* Header Styles */
header {
  background-color: #333;
  color: #fff;
  padding: 20px;
}

nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.logo img {
  max-height: 50px;
}

nav ul {
  list-style-type: none;
  display: flex;
  margin: 0;
  padding: 0;
}

nav li {
  margin-right: 20px;
}

nav a {
  color: #fff;
  text-decoration: none;
  transition: color 0.3s;
}

nav a:hover {
  color: #4CAF50;
}

.auth button {
  background-color: #4CAF50;
  border: none;
  color: #fff;
  padding: 10px 20px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  margin-left: 10px;
  cursor: pointer;
  transition: background-color 0.3s;
}

.auth button:hover {
  background-color: #45a049;
}

/* Hero Section Styles */
.hero {
  background-image: url('hero-bg.jpg');
  background-size: cover;
  background-position: center;
  color: #fff;
  padding: 100px 20px;
  text-align: center;
  position: relative;
}

.hero::after {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
}

.hero-content {
  position: relative;
  z-index: 1;
  max-width: 600px;
  margin: 0 auto;
}

.hero h1 {
  font-size: 48px;
  margin-bottom: 20px;
}

.hero p {
  font-size: 24px;
  margin-bottom: 40px;
}

.cta {
  background-color: #4CAF50;
  border: none;
  color: #fff;
  padding: 15px 32px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  margin-top: 20px;
  cursor: pointer;
  transition: background-color 0.3s;
}

.cta:hover {
  background-color: #45a049;
}

/* Categories Section Styles */
.categories {
  padding: 60px 20px;
  text-align: center;
}

.categories h2 {
  font-size: 36px;
  margin-bottom: 40px;
}

.category-list {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
}

.category-item {
  width: 200px;
  margin: 20px;
  transition: transform 0.3s;
}

.category-item:hover {
  transform: scale(1.05);
}

.category-item img {
  width: 100%;
  height: 200px;
  object-fit: cover;
  border-radius: 10px;
}

.category-item h3 {
  margin-top: 10px;
}

/* Featured Products Section Styles */
.featured-products {
  background-color: #f2f2f2;
  padding: 60px 20px;
  text-align: center;
}

.featured-products h2 {
  font-size: 36px;
  margin-bottom: 40px;
}

.product-list {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
}

.product-item {
  width: 300px;
  margin: 20px;
  background-color: #fff;
  border-radius: 10px;
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
  padding: 20px;
  transition: transform 0.3s;
}

.product-item:hover {
  transform: scale(1.05);
}

.product-item img {
  width: 100%;
  height: 300px;
  object-fit: cover;
  border-radius: 10px;
}

.product-item h3 {
  margin-top: 20px;
}

.price {
  color: #4CAF50;
  font-weight: bold;
  margin-top: 10px;
}

.buy-btn {
  background-color: #4CAF50;
  border: none;
  color: #fff;
  padding: 10px 20px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  margin-top: 20px;
  cursor: pointer;
  transition: background-color 0.3s;
}

.buy-btn:hover {
  background-color: #45a049;
}

/* Testimonials Section Styles */
.testimonials {
  padding: 60px 20px;
  text-align: center;
}

.testimonials h2 {
  font-size: 36px;
  margin-bottom: 40px;
}

.testimonial-list {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
}

.testimonial-item {
  width: 300px;
  margin: 20px;
  background-color: #f2f2f2;
  border-radius: 10px;
  padding: 20px;
  transition: transform 0.3s;
}

.testimonial-item:hover {
  transform: scale(1.05);
}

.testimonial-item img {
  width: 80px;
  height: 80px;
  object-fit: cover;
  border-radius: 50%;
}

.testimonial-item h3 {
  margin-top: 20px;
}

.my-card {
  width: 100%;
  max-width: 300px;
}

/* Footer Styles */
footer {
  background-color: #333;
  color: #fff;
  padding: 40px 20px;
  text-align: center;
}

.footer-content {
  display: flex;
  justify-content: space-around;
  flex-wrap: wrap;
}

.footer-content h3 {
  margin-bottom: 20px;
}

.footer-content ul {
  list-style-type: none;
  padding: 0;
}

.footer-content li {
  margin-bottom: 10px;
}

.footer-content a {
  color: #fff;
  text-decoration: none;
  transition: color 0.3s;
}

.footer-content a:hover {
  color: #4CAF50;
}

.copyright {
  margin-top: 40px;
}
</style>