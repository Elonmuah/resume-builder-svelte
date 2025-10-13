<script>
  import Navbar from "./components/HeroSection/Navbar.svelte";
  import Main from "./components/Main.svelte";
  import Footer from "./components/Footer.svelte";
</script>

<div class="relative flex flex-col min-h-screen min-w-screen text-gray-100 overflow-hidden">

  <!-- Full-page gradient background -->
  <div class="fixed inset-0 min-h-full bg-gradient-to-br from-indigo-900 via-slate-950 to-cyan-700 -z-10"></div>

  <!-- Glow overlays -->
  <div class="fixed inset-0 min-h-full bg-[radial-gradient(circle_at_top_left,rgba(255,105,180,0.15)_0%,transparent_70%)] -z-10"></div>
  <div class="fixed inset-0 min-h-full bg-[radial-gradient(circle_at_bottom_right,rgba(0,255,255,0.1)_0%,transparent_80%)] -z-10"></div>

  <!-- Navbar -->
  <header class="relative z-10 w-full">
    <Navbar title="Resume Maker" />
  </header>

  <!-- Main content starts in middle of viewport -->
  <main class="relative z-10 flex-grow flex items-start justify-center min-h-[100vh]">
    <div class="flex flex-col justify-center h-screen w-full max-w-6xl px-4">
      <Main />
    </div>
  </main>

  <!-- Footer stays below content -->
  <footer class="relative z-10 w-full mt-auto">
    <Footer />
  </footer>
</div>