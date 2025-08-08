<script>
	import { onMount } from 'svelte';
	import ClickerGame from './day5/ClickerGame.svelte';
	import HorseRace from './day2/HorseRace.svelte';
	import SolarSystem from './day4-2/SolarSystem.svelte';

	let scrollY = 0;

	onMount(() => {
		const handleScroll = () => (scrollY = window.scrollY);
		window.addEventListener('scroll', handleScroll);
		return () => window.removeEventListener('scroll', handleScroll);
	});
</script>

<svelte:window bind:scrollY />

<div class="relative overflow-hidden">
	<!-- Hero Section with Parallax Cityscape -->
	<section
		class="relative flex h-screen items-center justify-center bg-gradient-to-b from-blue-400 via-blue-500 to-green-400"
	>
		<!-- Stars Background (slowest) -->
		<div class="absolute inset-0 opacity-80" style="transform: translateY({scrollY * 0.1}px)">
			<div class="absolute top-10 left-10 h-1 w-1 animate-pulse rounded-full bg-white"></div>
			<div
				class="absolute top-20 right-20 h-1 w-1 animate-pulse rounded-full bg-white delay-100"
			></div>
			<div
				class="absolute top-32 left-1/4 h-1 w-1 animate-pulse rounded-full bg-white delay-200"
			></div>
			<div
				class="absolute top-16 right-1/3 h-1 w-1 animate-pulse rounded-full bg-white delay-300"
			></div>
			<div
				class="absolute top-40 left-3/4 h-1 w-1 animate-pulse rounded-full bg-white delay-400"
			></div>
			<div
				class="absolute top-24 left-1/2 h-1 w-1 animate-pulse rounded-full bg-white delay-500"
			></div>
		</div>

		<!-- Moon (slow parallax) -->
		<div
			class="absolute top-20 right-20 h-24 w-24 rounded-full bg-yellow-100 opacity-90 shadow-lg"
			style="transform: translateY({scrollY * 0.2}px)"
		>
			<div class="absolute top-2 left-2 h-3 w-3 rounded-full bg-yellow-50 opacity-60"></div>
			<div class="absolute right-4 bottom-3 h-2 w-2 rounded-full bg-yellow-50 opacity-40"></div>
		</div>

		<!-- Far Mountains (medium parallax) -->
		<div
			class="absolute right-0 bottom-0 left-0 h-48"
			style="transform: translateY({scrollY * 0.3}px)"
		>
			<svg viewBox="0 0 1200 200" class="h-full w-full">
				<polygon
					points="0,200 0,120 200,60 400,100 600,40 800,80 1000,20 1200,60 1200,200"
					fill="#1e293b"
					opacity="0.7"
				/>
			</svg>
		</div>

		<!-- City Skyline (faster parallax) -->
		<div
			class="absolute right-0 bottom-0 left-0 z-10"
			style="transform: translateY({scrollY * 0.5}px)"
		>
			<!-- Building 1 -->
			<div class="absolute bottom-0 left-10 h-64 w-20 bg-gray-800">
				<div class="absolute top-4 left-2 h-3 w-3 bg-yellow-300"></div>
				<div class="absolute top-4 right-2 h-3 w-3 bg-yellow-300"></div>
				<div class="absolute top-12 left-2 h-3 w-3 bg-yellow-300"></div>
				<div class="absolute top-20 right-2 h-3 w-3 bg-yellow-300"></div>
				<div class="absolute top-28 left-2 h-3 w-3 bg-blue-300"></div>
			</div>

			<!-- Building 2 (tallest) -->
			<div class="absolute bottom-0 left-40 h-80 w-24 bg-gray-700">
				<div class="absolute top-2 left-2 h-4 w-4 bg-red-400"></div>
				<div class="absolute top-2 right-2 h-4 w-4 bg-red-400"></div>
				<div class="absolute top-10 left-2 h-4 w-4 bg-yellow-300"></div>
				<div class="absolute top-10 right-2 h-4 w-4 bg-yellow-300"></div>
				<div class="absolute top-18 left-2 h-4 w-4 bg-green-300"></div>
				<div class="absolute top-18 right-2 h-4 w-4 bg-blue-300"></div>
				<div class="absolute top-26 left-2 h-4 w-4 bg-yellow-300"></div>
				<div class="absolute top-34 right-2 h-4 w-4 bg-purple-300"></div>
			</div>

			<!-- Building 3 -->
			<div class="absolute bottom-0 left-72 h-48 w-16 bg-gray-600">
				<div class="absolute top-4 left-1 h-2 w-2 bg-yellow-300"></div>
				<div class="absolute top-4 right-1 h-2 w-2 bg-yellow-300"></div>
				<div class="absolute top-12 left-1 h-2 w-2 bg-blue-300"></div>
				<div class="absolute top-20 right-1 h-2 w-2 bg-green-300"></div>
			</div>

			<!-- Building 4 -->
			<div class="absolute right-40 bottom-0 h-72 w-20 bg-gray-800">
				<div class="absolute top-6 left-2 h-3 w-3 bg-cyan-300"></div>
				<div class="absolute top-6 right-2 h-3 w-3 bg-cyan-300"></div>
				<div class="absolute top-16 left-2 h-3 w-3 bg-yellow-300"></div>
				<div class="absolute top-16 right-2 h-3 w-3 bg-yellow-300"></div>
				<div class="absolute top-26 left-2 h-3 w-3 bg-pink-300"></div>
				<div class="absolute top-36 right-2 h-3 w-3 bg-blue-300"></div>
			</div>

			<!-- Building 5 -->
			<div class="absolute right-10 bottom-0 h-56 w-18 bg-gray-700">
				<div class="absolute top-4 left-1 h-2 w-2 bg-orange-300"></div>
				<div class="absolute top-4 right-1 h-2 w-2 bg-orange-300"></div>
				<div class="absolute top-12 left-1 h-2 w-2 bg-yellow-300"></div>
				<div class="absolute top-20 right-1 h-2 w-2 bg-red-300"></div>
			</div>
		</div>

		<!-- Title Text (no parallax - stays fixed) -->
		<div class="relative z-20 text-center text-white">
			<h1 class="mb-4 text-6xl font-bold drop-shadow-lg">My Portfolio</h1>
			<p class="text-xl opacity-90 drop-shadow">Scroll down to explore the parallax effect</p>
			<div class="mt-8 animate-bounce">
				<svg class="mx-auto h-8 w-8" fill="currentColor" viewBox="0 0 20 20">
					<path
						fill-rule="evenodd"
						d="M5.293 7.293a1 1 0 011.414 0L10 10.586l3.293-3.293a1 1 0 111.414 1.414l-4 4a1 1 0 01-1.414 0l-4-4a1 1 0 010-1.414z"
						clip-rule="evenodd"
					/>
				</svg>
			</div>
		</div>
	</section>

	<!-- About Me (Profile picture, name, brief description) -->
	<section class="relative z-30 bg-gray-900 text-white">
		<div class="mx-auto max-w-4xl px-8 py-20">
			<div class="flex w-full items-center rounded-full bg-gray-700 p-2">
				<div class="flex h-12 w-12 items-center justify-center rounded-full bg-gray-800">
					<div class="profile-image h-10 w-10 rounded-full bg-cover bg-center"></div>
				</div>
				<div class="ml-2">
					<h2 class="text-4xl font-bold">Ryan</h2>
					<div class="text-xs text-gray-400 italic">Student</div>
				</div>
			</div>
			<div class="grid gap-12 md:grid-cols-2">
				<div>
					<h3 class="mb-4 text-2xl font-semibold text-cyan-400">About me</h3>
					<p class="text-lg leading-relaxed text-gray-300">not old</p>
				</div>
				<div>
					<h3 class="mb-4 text-2xl font-semibold text-purple-400">Contact me</h3>
					<div class="text-lg leading-relaxed text-gray-300">
						<div class="font-semibold text-blue-400"><a href="trkckfr@gmail.com">Email Me</a></div>
					</div>
				</div>
			</div>
		</div>
	</section>
	<!-- My projects -->
	<section class="relative z-30 bg-gray-800 text-white">
		<div class="mx-auto max-w-4xl px-8 py-20">
			<h2 class="mb-8 text-center text-4xl font-bold">My projects</h2>
			<div class="flex flex-col space-y-5">
				<div class="rounded-lg bg-gray-700 p-6 text-center">
					<h3 class="mb-3 text-xl font-semibold text-blue-400">Clicker Game</h3>
					<div class="overflow-hidden rounded">
						<ClickerGame />
					</div>
				</div>
				<div class="rounded-lg bg-gray-700 p-6 text-center">
					<h3 class="mb-3 text-xl font-semibold text-green-400">Horse Race Simulator</h3>
					<div class="overflow-hidden rounded">
						<HorseRace />
					</div>
				</div>
				<div class="rounded-lg bg-gray-700 p-6 text-center">
					<h3 class="mb-3 text-xl font-semibold text-pink-400">Solar System Model</h3>
					<div class="overflow-hidden rounded">
						<SolarSystem />
					</div>
				</div>
			</div>
		</div>
	</section>

	<!-- Footer with scroll-to-top -->
	<section class="relative z-30 bg-black py-12 text-center text-white">
		<button
			on:click={() => window.scrollTo({ top: 0, behavior: 'smooth' })}
			class="rounded-full bg-gradient-to-r from-blue-500 to-purple-500 px-8 py-3 font-semibold transition-transform duration-200 hover:scale-105"
		>
			Back to Top ⬆️
		</button>
	</section>
</div>

<style>
	:global(html) {
		scroll-behavior: smooth;
	}

	.profile-image {
		background-image: url(https://i.imgur.com/PawkSZa.jpeg);
	}
</style>
