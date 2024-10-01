<template>
  <div>
    <!-- Navbar -->
    <nav :class="{'navbar': true, 'navbar-blur': isScrolled}" class="fixed-top w-100 mb-4">
      <div class="container">
        <!-- Nama toko di sebelah kiri -->
        <NuxtLink class="navbar-brand" to="/">Gege Gaming Store</NuxtLink>

        <!-- Navbar Links (contoh Home, About) -->
        <div>
          <ul class="navbar-nav d-flex flex-row">
            <li>
                <NuxtLink to=/login class="btn btn-outline-info">Login</NuxtLink>
            </li>
          </ul>
        </div>
      </div>
    </nav>

    <!-- Content of the page will be rendered here -->
    <nuxt />

    <!-- Footer -->
    <footer class="bg-dark text-white text-center p-3 mt-5">
      <div class="container">
        <p>&copy; 2024 Gege Gaming Store.</p>
      </div>
    </footer>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isScrolled: false,
    };
  },
  mounted() {
    window.addEventListener("scroll", this.handleScroll);
  },
  beforeDestroy() {
    window.removeEventListener("scroll", this.handleScroll);
  },
  methods: {
    handleScroll() {
      // Jika halaman di-scroll lebih dari 50px, isScrolled menjadi true
      this.isScrolled = window.scrollY > 50;
    },
  },
};
</script>

<style scoped>
/* Navbar default styles */
.navbar {
  padding: 1rem 1rem;
  background: rgba(250, 239, 239, 0.8); /* Warna dasar sebelum scroll */
  transition: background 0.3s ease, backdrop-filter 0.3s ease;
}

/* Tambahkan efek blur saat scroll */
.navbar-blur {
  background: rgba(255, 255, 255, 0.5); /* Warna setelah scroll dengan opacity lebih rendah */
  backdrop-filter: blur(10px); /* Efek blur */
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1); /* Sedikit shadow untuk perbedaan visual */
}

/* Styling links */
.nav-link {
  margin-right: 1rem;
  font-size: 1rem;
  color: #000;
  text-decoration: none;
}


.navbar-brand {
  font-size: 1.5rem;
  font-weight: bold;
  color: #000;
}

.navbar-brand:hover {
  color: #2c8bf8;
}

/* Responsiveness */
@media (max-width: 768px) {
  .navbar-nav {
    flex-direction: column;
  }
}
</style>
