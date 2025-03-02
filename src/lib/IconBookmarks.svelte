<script lang="ts">
	import Icon from "@iconify/svelte";

	const data = [
		{ name: "youtube", url: "https://youtube.com", icon: "iconoir:youtube-solid" },
		{ name: "reddit", url: "https://reddit.com", icon: "fa6-brands:reddit" },
		{ name: "bluesky", url: "https://bluesky.app", icon: "ri:bluesky-fill" },
		{ name: "twitter", url: "https://twitter.com", icon: "mdi:twitter" },
		{ name: "twitch", url: "https://twitch.tv", icon: "mdi:twitch" },
		{ name: "github", url: "https://github.com", icon: "mdi:github" },
		{ name: "last.fm", url: "https://last.fm", icon: "fa6-brands:lastfm" },
	];
</script>

<div class="flex justify-between mb-4">
	{#each data as bookmark}
		<a href={bookmark.url} data-tooltip={bookmark.name}>
			<Icon icon={bookmark.icon} width="32" height="32" class="transition duration-200 hover:text-accent" />
		</a>
	{/each}
</div>
