<script>
  import NavActions from "./NavActions.svelte";

  import { onMount } from "svelte";
  let h1Ref;
  let fontSize = 24; // initial size

  onMount(() => {
    const resize = () => {
      const parentWidth = h1Ref?.parentElement?.offsetWidth || 0;
      fontSize = parentWidth / 8; // tweak divisor for size
    };
    resize();
    window.addEventListener("resize", resize);
    return () => window.removeEventListener("resize", resize);
  });

  export let title = "Resume Builder";
</script>

<nav class="absolute inset-x-0 top-0 h-16">
  <div class="flex flex-wrap h-full">
    <div class="w-1/2 bg-gray-300 flex items-center justify-center">
      <h1
        bind:this={h1Ref}
        class="font-bold text-center"
        style="font-size: {fontSize}px; line-height: 1;"
      >
        {title}
      </h1>
    </div>
    <div class="w-1/4 bg-gray-400 flex items-center justify-center">
    </div>
    <div class="w-1/4 bg-gray-500 flex items-center justify-center">
      <NavActions />
    </div>
  </div>
</nav>
