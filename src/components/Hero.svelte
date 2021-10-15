<script>
  import GoogleButton from "./GoogleButton.svelte";
</script>

<section class="min-h-screen bg-gray-100 p-32 text-center">
  <h1 class="text-5xl font-bold text-blue-700 mb-2">QR <span class="text-purple-400">@</span></h1>
  <p class="text-gray-700 text-lg mb-12">The all new attendance tracking system!</p>
  <GoogleButton on:click={() => console.log("Hello")} />
</section>
