<script lang="ts">
	import { fade, fly } from "svelte/transition";
	import Icon from "@iconify/svelte";

	let open = true;
	let animationState = "paused";
</script>

<div class="absolute bottom-4 right-4 size-6 flex flex-row-reverse gap-4">
	<button class="cursor-pointer transition-transform duration-100 active:scale-90">
		<Icon
			icon="material-symbols:settings-rounded"
			width="24"
			height="24"
			class="opacity-50 hover:opacity-100 transition-opacity animate-[spin_4s_linear_infinite] {open ? 'opacity-100' : ''}"
			style="animation-play-state: {animationState};"
			onpointerenter={() => (open ? null : (animationState = "playing"))}
			onpointerleave={() => (open ? null : (animationState = "paused"))}
			onclick={() => (open = !open)}
		/>
	</button>

	{#if open}
		<div transition:fly={{ x: 10 }} class="absolute right-8 top-1/2 -translate-y-1/2 bg-base border border-text/50 rounded-lg shadow flex gap-1 p-1">
			<button class="button">
				<Icon icon="material-symbols:add-rounded" width="24" height="24" />
				add
			</button>
			<button class="button">
				<Icon icon="fluent:paint-brush-24-filled" width="24" height="24" />
				theme
			</button>

			<button class="p-1 cursor-pointer transition hover:opacity-65" onclick={() => (open = false)}>
				<Icon icon="material-symbols:close-rounded" width="24" height="24" />
			</button>
		</div>
	{/if}
</div>

{#if open}
	<!-- construction border effect -->
	<div transition:fade={{ duration: 100 }} class="absolute top-0 left-0 w-full h-full border-2 border-dashed border-text/50 -z-10"></div>
{/if}
