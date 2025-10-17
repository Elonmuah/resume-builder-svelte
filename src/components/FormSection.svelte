<script>
    import Navbar from "./HeroSection/Navbar.svelte";
    import jsPDF from "jspdf";

    let name = "";
    let jobTitle = "";
    let summary = "";

    const generatePDF = () => {
        const doc = new jsPDF();

        doc.setFont("helvetica", "bold");
        doc.setFontSize(20);
        doc.text("Resume", 20, 20);

        doc.setFont("helvetica", "normal");
        doc.setFontSize(12);
        doc.text(`Name: ${name}`, 20, 40);
        doc.text(`Job Title: ${jobTitle}`, 20, 50);
        doc.text(`Summary: ${summary}`, 20, 70);

        doc.save(`${name || "resume"}.pdf`);
    };
</script>

<div class="relative flex flex-col min-h-screen min-w-screen text-gray-100 overflow-hidden bg-gray-950/50">
  <header class="z-10 w-full">
    <Navbar />
  </header>

  <!--Form section (A4 ratio)-->
  <div class="flex justify-center items-start py-12">
    <div
      class="bg-gray-900/70 p-6 rounded-2xl shadow-lg w-full max-w-[800px]"
      style="aspect-ratio: 210 / 297; min-height: 400px;"
    >
      <h2 class="text-2xl font-semibold mb-4 text-indigo-400">Build Your Resume</h2>

      <input class="w-full p-2 mb-2 rounded bg-gray-800 border border-gray-600" placeholder="Your Name" bind:value={name} />
      <input class="w-full p-2 mb-2 rounded bg-gray-800 border border-gray-600" placeholder="Job Title" bind:value={jobTitle} />
      <textarea class="w-full p-2 mb-2 rounded bg-gray-800 border border-gray-600 h-32" placeholder="Short Summary" bind:value={summary}></textarea>

      <button
        class="mt-4 w-full bg-gradient-to-r from-green-400 to-blue-500 text-white py-2 rounded-lg font-semibold hover:scale-105 transition-transform"
        on:click={generatePDF}
      >
        Generate PDF
      </button>
    </div>
  </div>
</div>
