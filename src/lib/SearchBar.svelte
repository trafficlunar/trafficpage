<script lang="ts">
	import Icon from '@iconify/svelte';

  let searchValue = $state("");

  function submitSearch() {
    window.location.href = `https://www.google.com/search?q=${searchValue}`;
  }

  function searchOnEnter(e: KeyboardEvent) {
    if (e.key == "Enter") submitSearch();
  }
</script>

<div class="ring-accent/50 focus-within:border-accent rounded-lg border-2 focus-within:ring-3 transition duration-200">
	<button onclick={submitSearch} class="absolute flex size-12 items-center justify-center">
		<Icon icon="lets-icons:search" width="24" height="24" />
	</button>

	<!-- svelte-ignore a11y_autofocus -->
	<input type="text" placeholder="Search" onkeydown={searchOnEnter} bind:value={searchValue} class="w-full p-3 ps-12 outline-none placeholder:text-overlay" autofocus />
</div>
