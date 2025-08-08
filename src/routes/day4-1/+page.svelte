<script>
	import { onMount } from 'svelte';

	let scrollY = 0;

	onMount(() => {
		const handleScroll = () => (scrollY = window.scrollY);
		window.addEventListener('scroll', handleScroll);
		return () => window.removeEventListener('scroll', handleScroll);
	});
</script>

<svelte:window bind:scrollY />

<div>
	<section
		class="relative flex h-screen items-center justify-center bg-gradient-to-b from-purple-900 via-blue-900 to-indigo-900 text-white"
	>
		<!-- stars -->
		<div class="absolute top-10 left-15 h-1 w-1 animate-pulse rounded-full bg-white/70"></div>
		<div class="absolute top-10 right-40 h-1 w-1 animate-pulse rounded-full bg-white/90"></div>
		<div class="absolute top-12 right-15 h-1 w-1 animate-pulse rounded-full bg-white/70"></div>
		<div class="absolute top-14 left-45 h-1 w-1 animate-pulse rounded-full bg-white/40"></div>
		<div class="absolute top-13 right-23 h-1 w-1 animate-pulse rounded-full bg-white/70"></div>
		<!-- moon -->
		<div
			class="absolute top-10 right-10 h-20 w-20 rounded-full bg-yellow-200/70"
			style="transform: translateY({scrollY * 1.1}px)"
		></div>

		<!-- text -->
		<div class="text-center">
			<div class="ts-4xl font-bold" style="transform: translateY({scrollY * 1.1}px)">
				Night City {scrollY * 1.1}
			</div>
			<div>Scroll down to explore</div>
			<div class="animate-bounce">
				<svg class="mx-auto h-8 w-8" fill="currentColor" viewBox="0 0 20 20">
					<path
						fill-rule="evenodd"
						d="M5.293 7.293a1 1 0 011.414 0L10 10.586l3.293-3.293a1 1 0 111.414 1.414l-4 4a1 1 0 01-1.414 0l-4-4a1 1 0 010-1.414z"
						clip-rule="evenodd"
					/>
				</svg>
			</div>
		</div>

		<!-- mountain -->
		<div class="absolute right-0 -bottom-3 left-0 z-100 h-48">
			<svg viewBox="0 0 1200 200" class="h-full w-full">
				<polygon
					points="0,200 0,120 200,60 400,100 600,40 800,80 1000,20 1200,60 1200,200"
					fill="#1e293b"
					opacity="0.7"
				/>
			</svg>
		</div>

		<!-- buildings -->
		<div class="z-200">
			<div class="absolute bottom-0 left-10 h-70 w-20 bg-gray-700">
				<div class="absolute top-5 left-2 h-5 w-5 bg-yellow-300"></div>
				<div class="absolute top-5 right-2 h-5 w-5 bg-yellow-300"></div>
				<div class="absolute top-15 left-2 h-5 w-5 bg-yellow-300"></div>
				<div class="absolute top-30 right-2 h-5 w-5 bg-yellow-300"></div>
				<div class="absolute top-40 left-2 h-5 w-5 bg-gray-300"></div>
			</div>

			<div class="absolute bottom-0 left-40 h-60 w-17 bg-neutral-800">
				<div class="absolute top-5 left-2 h-5 w-5 bg-yellow-300"></div>
				<div class="absolute top-20 right-2 h-5 w-5 bg-yellow-300"></div>
			</div>

			<div class="absolute bottom-0 left-70 h-90 w-25 bg-gray-800">
				<div class="absolute top-5 left-2 h-5 w-5 bg-yellow-300"></div>
				<div class="absolute top-20 right-2 h-5 w-5 bg-yellow-300"></div>
			</div>

			<div class="absolute right-10 bottom-0 h-70 w-20 bg-gray-700">
				<div class="absolute top-5 left-2 h-5 w-5 bg-yellow-300"></div>
				<div class="absolute top-5 right-2 h-5 w-5 bg-yellow-300"></div>
				<div class="absolute top-15 left-2 h-5 w-5 bg-yellow-300"></div>
				<div class="absolute top-30 right-2 h-5 w-5 bg-yellow-300"></div>
				<div class="absolute top-40 left-2 h-5 w-5 bg-gray-300"></div>
			</div>

			<div class="absolute right-40 bottom-0 h-60 w-17 bg-neutral-800">
				<div class="absolute top-5 left-2 h-5 w-5 bg-yellow-300"></div>
				<div class="absolute top-20 right-2 h-5 w-5 bg-yellow-300"></div>
			</div>

			<div class="absolute right-70 bottom-0 h-90 w-25 bg-gray-800">
				<div class="absolute top-5 left-2 h-5 w-5 bg-yellow-300"></div>
				<div class="absolute top-20 right-2 h-5 w-5 bg-yellow-300"></div>
			</div>
		</div>
	</section>
	<section class="relative z-30 bg-gray-800 text-white">
		<div class="mx-auto max-w-4xl px-8 py-20">
			<h2 class="mb-8 text-center text-4xl font-bold">City Features</h2>
			<div class="grid gap-8 md:grid-cols-3">
				<div class="rounded-lg bg-gray-700 p-6 text-center">
					<div class="mb-4 text-4xl">🏢</div>
					<h3 class="mb-3 text-xl font-semibold text-blue-400">Skyscrapers</h3>
					<p class="text-gray-300">
						Magnificent towers that define the city skyline and house thousands of dreams.
					</p>
				</div>
				<div class="rounded-lg bg-gray-700 p-6 text-center">
					<div class="mb-4 text-4xl">🚗</div>
					<h3 class="mb-3 text-xl font-semibold text-green-400">Transport</h3>
					<p class="text-gray-300">
						Efficient networks connecting every corner of the metropolitan area.
					</p>
				</div>
				<div class="rounded-lg bg-gray-700 p-6 text-center">
					<div class="mb-4 text-4xl">🎭</div>
					<h3 class="mb-3 text-xl font-semibold text-pink-400">Culture</h3>
					<p class="text-gray-300">
						Rich arts, entertainment, and diverse communities creating vibrant neighborhoods.
					</p>
				</div>
			</div>
		</div>
	</section>

	<section class="relative z-30 bg-gray-900 text-white">
		<div class="mx-auto max-w-4xl px-8 py-20">
			<h2 class="mb-8 text-4xl font-bold">The Parallax Effect</h2>
			<div class="prose max-w-none prose-invert">
				<h3 class="mb-4 text-2xl font-semibold text-yellow-400">🎨 What We're Learning</h3>
				<ul class="space-y-3 text-lg">
					<li>
						<strong>CSS Transforms:</strong>
						<code class="rounded bg-gray-700 px-2 py-1">transform: translateY()</code>
					</li>
					<li>
						<strong>Scroll Events:</strong>
						<code class="rounded bg-gray-700 px-2 py-1">window.scrollY</code>
					</li>
					<li>
						<strong>Layering:</strong> <code class="rounded bg-gray-700 px-2 py-1">z-index</code>
						and <code class="rounded bg-gray-700 px-2 py-1">position: absolute</code>
					</li>
					<li>
						<strong>Gradients:</strong>
						<code class="rounded bg-gray-700 px-2 py-1">bg-gradient-to-b</code>
					</li>
					<li>
						<strong>Animations:</strong>
						<code class="rounded bg-gray-700 px-2 py-1">animate-pulse</code>,
						<code class="rounded bg-gray-700 px-2 py-1">animate-bounce</code>
					</li>
				</ul>

				<h3 class="mt-8 mb-4 text-2xl font-semibold text-green-400">🔧 How It Works</h3>
				<p class="text-lg text-gray-300">
					Different elements move at different speeds as you scroll, creating depth and immersion.
					The stars move slowest, mountains medium speed, and buildings fastest, creating the
					illusion of 3D space on a 2D screen!
				</p>
			</div>
		</div>
	</section>

	<!-- Footer with scroll-to-top -->
	<section class="relative z-30 bg-black py-12 text-center text-white">
		<h3 class="mb-4 text-2xl font-bold">Keep Exploring! 🚀</h3>
		<p class="mb-6 text-gray-400">Scroll back up to see the parallax effect in reverse</p>
		<button
			on:click={() => window.scrollTo({ top: 0, behavior: 'smooth' })}
			class="rounded-full bg-gradient-to-r from-blue-500 to-purple-500 px-8 py-3 font-semibold transition-transform duration-200 hover:scale-105"
		>
			Back to Top ⬆️
		</button>
	</section>
</div>

<style>
	.ts-4xl {
		font-size: 2.25rem;
		line-height: 2.5rem;
	}

	:global(html) {
		scroll-behavior: smooth;
	}
</style>
