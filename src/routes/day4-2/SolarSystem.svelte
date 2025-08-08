<div class="relative h-screen overflow-hidden bg-gradient-to-b from-black via-purple-900 to-black">
	<div class="centered h-8 w-8 rounded-full bg-yellow-200"></div>
	<!-- mercury -->
	<div
		class="centered h-12 w-12 animate-[spin_8s_linear_infinite] rounded-full border border-gray-200/40"
	>
		<div
			class="absolute h-2 w-2 translate-0.5 animate-[spin_1s_linear_infinite] rounded-full bg-gray-300"
		></div>
	</div>

	<!-- venus -->
	<div
		class="centered h-20 w-20 animate-[spin_12s_linear_infinite] rounded-full border border-gray-200/40"
	>
		<div
			class="absolute h-2 w-2 translate-2 animate-[spin_2s_linear_infinite] rounded-full bg-amber-500"
		></div>
	</div>

	<!-- earth -->
	<div
		class="centered h-30 w-30 animate-[spin_16s_linear_infinite] rounded-full border border-gray-200/40"
	>
		<div
			class="absolute h-2 w-2 translate-3.5 animate-[spin_3s_linear_infinite] rounded-full bg-gradient-to-r from-blue-400 via-blue-500 to-green-500"
		>
			<div class="h-1 w-1 -translate-[6px] rounded-full bg-white"></div>
		</div>
	</div>

	<!-- mars -->
	<div
		class="centered h-38 w-38 animate-[spin_24s_linear_infinite] rounded-full border border-gray-200/40"
	>
		<div
			class="absolute h-2 w-2 translate-4.5 animate-[spin_4s_linear_infinite] rounded-full bg-gradient-to-r from-amber-600 via-amber-700 to-orange-700"
		></div>
	</div>

	<!-- jupiter -->
	<div
		class="centered h-46 w-46 animate-[spin_32s_linear_infinite] rounded-full border border-gray-200/40"
	>
		<div
			class="absolute h-2 w-2 translate-5.5 animate-[spin_5s_linear_infinite] rounded-full bg-gradient-to-r from-orange-500 via-neutral-100 to-orange-500"
		></div>
	</div>

	<!-- saturn -->
	<div
		class="centered h-54 w-54 animate-[spin_40s_linear_infinite] rounded-full border border-gray-200/40"
	>
		<div
			class="absolute h-2 w-2 translate-7 animate-[spin_6s_linear_infinite] rounded-full bg-gradient-to-r from-orange-300 via-white to-orange-300"
		>
			<div class="centered h-5 w-5 rounded-full border border-2 border-white"></div>
		</div>
	</div>

	<!-- uranus -->
	<div
		class="centered h-62 w-62 animate-[spin_50s_linear_infinite] rounded-full border border-gray-200/40"
	>
		<div
			class="absolute h-2 w-2 translate-8 animate-[spin_7s_linear_infinite] rounded-full bg-gradient-to-r from-blue-500 via-neutral-100 to-sky-500"
		></div>
	</div>

	<!-- neptune -->
	<div
		class="centered h-70 w-70 animate-[spin_60s_linear_infinite] rounded-full border border-gray-200/40"
	>
		<div
			class="absolute h-2 w-2 translate-9 animate-[spin_8s_linear_infinite] rounded-full bg-gradient-to-r from-blue-700 via-indigo-800 to-blue-800"
		></div>
	</div>

	<!-- stars -->
	{#each Array(100) as _, __}
		<div
			class="absolute h-0.5 w-0.5 animate-pulse rounded-full bg-white/90"
			style="top: {Math.random() * 90}vh; left: {Math.random() *
				90}vw; animation-delay: {Math.random() * 250}ms;"
		></div>
	{/each}
</div>

<style>
	.centered {
		@apply absolute top-1/2 left-1/2 -translate-1/2;
	}
</style>
