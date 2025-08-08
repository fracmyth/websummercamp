<script>
	let { current, max, color } = $props();
</script>

<div class="h-6 w-48 border">
	<div
		style="width: {(current / max) * 100}%"
		class="h-full transition-all duration-300 {color}"
	></div>
</div>
