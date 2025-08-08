<script>
	let { text, fn } = $props();
</script>

<button
	onclick={fn}
	class="m-1 cursor-pointer rounded-xl border border-2 border-double px-3 py-1 font-semibold tracking-wider shadow-2xl transition-all duration-200 hover:bg-black hover:text-white active:scale-110"
	>{text}</button
>
