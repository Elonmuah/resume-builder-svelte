<script>
  import Navbar from "./HeroSection/Navbar.svelte";
  import Main from "./Main.svelte";
  import Footer from "./Footer.svelte";
  import { createEventDispatcher } from 'svelte';
  const dispatch = createEventDispatcher();

  function handleStart() {
    dispatch('startForm');
  }
</script>

<div class="relative flex flex-col min-h-screen min-w-screen text-gray-100 overflow-hidden">

  <!-- Full-page gradient background -->
  <div class="fixed inset-0 bg-gradient-to-br from-indigo-900 via-slate-950 to-cyan-700 -z-10"></div>

  <!-- Glow overlays -->
  <div class="fixed inset-0 bg-[radial-gradient(circle_at_top_left,rgba(255,105,180,0.15)_0%,transparent_70%)] -z-10"></div>
  <div class="fixed inset-0 bg-[radial-gradient(circle_at_bottom_right,rgba(0,255,255,0.1)_0%,transparent_80%)] -z-10"></div>

  <!-- Navbar -->
  <header class="z-10 w-full">
    <Navbar />
  </header>

  <!-- Main content (starts roughly middle of viewport, never overlaps header/footer) -->
  <main class="z-10 flex-grow flex items-center justify-center py-20 sm:py-32 md:py-40">
    <div class="w-full max-w-6xl px-4">
      <Main on:startForm={handleStart}/>
    </div>
  </main>

  <!-- Footer (stays below content, scrolls naturally) -->
  <footer class="z-10 w-full mt-auto">
    <Footer />
  </footer>
</div>
