<script lang="ts">
	import Clock from "@/lib/Clock.svelte";
	import Bookmarks from "@/lib/Bookmarks.svelte";
	import IconBookmarks from "@/lib/IconBookmarks.svelte";
	import SearchBar from "@/lib/SearchBar.svelte";
	import Settings from "@/lib/Settings.svelte";
</script>

<Clock />

<main class="max-w-xl w-screen px-4">
	<IconBookmarks />
	<SearchBar />
	<Bookmarks />
</main>

<Settings />
