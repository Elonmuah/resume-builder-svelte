<script>
  import { createEventDispatcher } from "svelte";
  const dispatch = createEventDispatcher();
</script>

<div class="text-center justify-center flex flex-col items-center px-4 py-20" id="mainBlock">
  <!-- Heading -->
  <div>
    <p
      class="text-4xl md:text-6xl font-extrabold mb-6 text-transparent bg-clip-text
         bg-gradient-to-r from-cyan-400 via-indigo-400 to-purple-500
         drop-shadow-[0_0_10px_rgba(99,102,241,0.6)] animate-fadeIn
         leading-[1.2] pb-2 overflow-visible"
    >
      Crafted by you.<br />Perfected by us.
    </p>
  </div>

  <!-- Button -->
  <div class="mt-4">
    <button
    on:click={() => dispatch("startForm")}
    class="relative inline-flex items-center justify-center p-1 mb-3 me-2 overflow-hidden text-3xl font-semibold text-gray-900 rounded-xl group 
            bg-gradient-to-br from-green-400 to-blue-600 
            group-hover:from-green-400 group-hover:to-blue-600 
            hover:text-white dark:text-white 
            focus:ring-4 focus:outline-none focus:ring-green-200 dark:focus:ring-green-800 
            transition-all duration-300 scale-105 hover:scale-110 shadow-lg hover:shadow-xl"
    >
    <span
        class="relative px-8 py-4 transition-all ease-in duration-150 
            bg-white dark:bg-gray-900 rounded-lg 
            group-hover:bg-transparent group-hover:dark:bg-transparent"
    >
        Start Now
    </span>
  </button>
  </div>

  <!-- Features -->
  <div class="pt-12 flex flex-wrap gap-10 justify-center max-w-6xl" id="wrapit">
    <div class="w-80 text-justify">
      <h2 class="pb-3 text-3xl md:text-4xl">
        <strong class="text-red-500 font-semibold drop-shadow-[0_0_6px_rgba(99,102,241,0.8)]">F</strong>ree
      </h2>
      <p class="text-gray-300">
        Build your professional résumé without limits. No paywalls, no hidden catches — just powerful tools that let you design, customize, and download your résumé for free. Focus on your career, not your credit card.
      </p>
    </div>

    <div class="w-80 text-justify">
      <h2 class="pb-3 text-3xl md:text-4xl">
        <strong class="text-red-500 font-semibold drop-shadow-[0_0_6px_rgba(99,102,241,0.8)]">F</strong>ast
      </h2>
      <p class="text-gray-300">
        From start to finish in minutes. Our intuitive builder helps you generate, edit, and polish your résumé in real-time — no loading screens, no wasted effort. Just instant results that move as quickly as you do.
      </p>
    </div>

    <div class="w-80 text-justify">
      <h2 class="pb-3 text-3xl md:text-4xl">
        <strong class="text-red-500 font-semibold drop-shadow-[0_0_6px_rgba(99,102,241,0.8)]">F</strong>ormatted
      </h2>
      <p class="text-gray-300">
        Your résumé, perfectly aligned every time. With smart templates and adaptive layouts, every section looks clean, consistent, and ready for recruiters. Designed for precision — because presentation matters.
      </p>
    </div>
  </div>
  <!-- Templates -->
<div class="pt-16 flex flex-col items-start self-start w-full max-w-6xl px-8">
  <h2 class="text-2xl font-semibold mb-6 text-gray-100">
    Choose a template to get started:
  </h2>

  <!-- Template previews -->
  <div class="overflow-x-auto w-full">
    <!-- Template cards will go here -->
  </div>
</div>
</div>
