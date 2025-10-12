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

<nav class="absolute inset-x-0 top-0 h-vh">
  <div class="flex flex-wrap h-full bg-gradient-to-bl from-blue-800 via-slate-950 to-blue-500">
    <div class="w-1/2 flex items-center justify-center">
      <h1
        bind:this={h1Ref}
        class="font-bold text-center"
        style="font-size: {fontSize}px; line-height: 1;"
      >
        {title}
      </h1>
    </div>
    <div class="w-1/4 flex items-center justify-center">
    </div>
    <div class="w-1/4 flex items-center justify-center">
      <NavActions />
    </div>
  </div>
</nav>
