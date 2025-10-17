<script>
  import { onMount } from "svelte";

  let menuOpen = false;
  let isCollapsed = false;

  const toggleMenu = () => menuOpen = !menuOpen;

  const checkCollapse = () => {
    isCollapsed = window.innerWidth <= 1500; // collapse based on viewport
  };

  onMount(() => {
    checkCollapse(); // initial check
    window.addEventListener("resize", checkCollapse);
    return () => window.removeEventListener("resize", checkCollapse);
  });
</script>

<div class="flex items-center justify-end h-full">
  {#if isCollapsed}
    <!-- Dropdown -->
    <button id="buttonButton" on:click={toggleMenu} class="p-2 w-14 h-14 flex items-center justify-center text-gray-700 bg-gray-100 rounded-lg hover:bg-gray-200">
        <!-- Heroicons Menu Icon -->
        <svg xmlns="http://www.w3.org/2000/svg" class="w-6 h-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="3" d="M4 6h16M4 12h16M4 18h16" />
        </svg>
    </button>

    {#if menuOpen}
      <ul class="absolute top-16 right-0 flex flex-col p-4 mt-2 bg-white shadow-lg rounded-lg gap-2 w-40">
        <li><button id="buttonButton" class="w-full text-left px-2 py-1 bg-gray-100 rounded text-gray-700" on:click={()=>console.log('Login')}>Log in</button></li>
        <li><button id="buttonButton" class="w-full text-left px-2 py-1 bg-gray-100 rounded text-gray-700" on:click={()=>console.log('Signup')}>Sign up</button></li>
        <li><button id="buttonButton" class="w-full text-left px-2 py-1 bg-indigo-600 text-white rounded" on:click={()=>console.log('Premium')}>Go Premium</button></li>
      </ul>
    {/if}
  {:else}
    <!-- Regular buttons -->
    <div class="flex gap-2">
      <button id="buttonButton" class="px-4 py-2 bg-gray-100 rounded text-gray-700" on:click={()=>console.log('Login')}>Log in</button>
      <button id="buttonButton" class="px-4 py-2 bg-gray-100 rounded text-gray-700" on:click={()=>console.log('Signup')}>Sign up</button>
      <button id="buttonButton" class="px-4 py-2 bg-indigo-600 text-white rounded" on:click={()=>console.log('Premium')}>Go Premium</button>
    </div>
  {/if}
</div>
