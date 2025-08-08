<script>
	let { emote, position, color, animation } = $props();
</script>

<div class="flex h-10 items-center bg-orange-900">
	<div style="width:{position}%" class="{color} h-full shrink-0 transition-all duration-200"></div>
	<div class="animal {animation}">{emote}</div>
</div>

<style>
	.animal {
		font-size: 65px;
	}

	.bounce {
		animation: bounce 0.5s infinite;
	}
</style>
