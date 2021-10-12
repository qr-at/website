<script>
  import { fly } from "svelte/transition";

  let open = false;
</script>

<div class="w-full text-gray-700 bg-white">
  <div class="flex flex-col max-w-screen-xl px-4 mx-auto md:items-center md:justify-between md:flex-row md:px-6 lg:px-8">
    <div class="p-4 flex flex-row items-center justify-between">
      <a href="/" class="text-lg font-semibold tracking-widest text-gray-900 uppercase rounded-lg focus:outline-none focus:shadow-outline">QR <span class="text-purple-400">@</span></a>
      <button class="md:hidden rounded-lg focus:outline-none focus:shadow-outline" on:click={() => (open = !open)}>
        <svg fill="currentColor" viewBox="0 0 20 20" class="w-6 h-6">
          {#if open}
            <path fill-rule="evenodd" d="M4.293 4.293a1 1 0 011.414 0L10 8.586l4.293-4.293a1 1 0 111.414 1.414L11.414 10l4.293 4.293a1 1 0 01-1.414 1.414L10 11.414l-4.293 4.293a1 1 0 01-1.414-1.414L8.586 10 4.293 5.707a1 1 0 010-1.414z" clip-rule="evenodd"></path>
          {:else}
            <path fill-rule="evenodd" d="M3 5a1 1 0 011-1h12a1 1 0 110 2H4a1 1 0 01-1-1zM3 10a1 1 0 011-1h12a1 1 0 110 2H4a1 1 0 01-1-1zM9 15a1 1 0 011-1h6a1 1 0 110 2h-6a1 1 0 01-1-1z" clip-rule="evenodd"></path>
          {/if}
        </svg>
      </button>
    </div>
    {#if open}
      <nav class="md:hidden flex flex-col flex-grow pb-4" transition:fly="{{ y: -10, duration: 150 }}">
        <button class="px-4 py-2 mt-2 text-sm font-semibold text-gray-900 rounded-lg md:mt-0 hover:text-red-900 focus:text-red-900 hover:bg-red-200 focus:bg-red-200 focus:outline-none focus:shadow-outline">Login with Google</button>
      </nav>
    {/if}
    <nav class="hidden md:flex md:flex-row md:flex-grow md:justify-end md:pb-4 md:pb-0">
      <button class="px-4 py-2 mt-2 text-sm font-semibold text-gray-900 rounded-lg md:mt-0 hover:text-red-900 focus:text-red-900 hover:bg-red-200 focus:bg-red-200 focus:outline-none focus:shadow-outline">Login with Google</button>
    </nav>
  </div>
</div>
