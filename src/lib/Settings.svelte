<script lang="ts">
	import Icon from "@iconify/svelte";

	let animationState = "paused";
</script>

<button class="absolute bottom-4 right-4 cursor-pointer transition-transform duration-75 active:scale-90">
	<Icon
		icon="material-symbols:settings-rounded"
		width="24"
		height="24"
		class="opacity-50 hover:opacity-100 transition-opacity animate-[spin_3s_linear_infinite]"
		style="animation-play-state: {animationState};"
		onpointerenter={() => (animationState = "playing")}
		onpointerleave={() => (animationState = "paused")}
	/>
</button>
