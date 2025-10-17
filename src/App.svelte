<!-- App.svelte -->
<script>
  import MainPage from "./components/MainPage.svelte";
  import FormSection from "./components/FormSection.svelte";

  let currentPage = "main"; // default page

  function goToForm() {
    currentPage = "form";
  }

  function goBack() {
    currentPage = "main";
  }
</script>

<div class="flex flex-col min-h-screen">
  {#if currentPage === "main"}
    <MainPage on:startForm={goToForm} />
  {:else if currentPage === "form"}
    <FormSection on:goBack={goBack} />
  {/if}
</div>
