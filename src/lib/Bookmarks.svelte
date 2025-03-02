<script lang="ts">
	import Icon from "@iconify/svelte";

	const data = [
		[
			{ name: "youtube", url: "https://youtube.com", icon: "iconoir:youtube-solid" },
			{ name: "reddit", url: "https://reddit.com", icon: "fa6-brands:reddit" },
			{ name: "bluesky", url: "https://bluesky.app", icon: "ri:bluesky-fill" },
		],
		[
			{ name: "twitter", url: "https://twitter.com", icon: "mdi:twitter" },
			{ name: "twitch", url: "https://twitch.tv", icon: "mdi:twitch" },
			{ name: "github", url: "https://github.com", icon: "mdi:github" },
			{ name: "last.fm", url: "https://last.fm", icon: "fa6-brands:lastfm" },
		],
		[
			{ name: "twitter", url: "https://twitter.com", icon: "mdi:twitter" },
			{ name: "twitch", url: "https://twitch.tv", icon: "mdi:twitch" },
			{ name: "github", url: "https://github.com", icon: "mdi:github" },
			{ name: "last.fm", url: "https://last.fm", icon: "fa6-brands:lastfm" },
		],
	];
</script>

<div class="grid justify-between mt-2" style="grid-template-columns: repeat({data.length}, minmax(0, auto));">
	{#each data as category}
		<div class="flex flex-col gap-0.5">
			{#each category as bookmark}
				<a href={bookmark.url} class="flex items-center gap-1.5 w-min px-1.5 py-0.5 rounded transition-colors hover:bg-accent/15 hover:text-accent">
					<Icon icon={bookmark.icon} width="16" height="16" />
					{bookmark.name}
				</a>
			{/each}
		</div>
	{/each}
</div>
