<script>
  import Navbar from "./components/HeroSection/Navbar.svelte";
  import Main from "./components/Main.svelte";
  import Footer from "./components/Footer.svelte";
</script>

<div class="flex flex-col min-h-screen min-w-screen bg-[url('/src/assets/employment.jpg')] bg-cover">
  <!-- Navbar -->
  <header class="w-full">
    <Navbar title="Resume Maker" />
  </header>

  <!-- Main content -->
  <main class="flex-grow flex items-center justify-center"> 
    <Main />
  </main>
  <footer>
    <Footer />
  </footer>
</div>