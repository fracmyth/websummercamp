<script>
	import Horse from './Horse.svelte';
	import Button from '../../components/Button.svelte';
	//array of horses
	let horses = $state([
		{
			emote: '🔲',
			position: 0,
			color: 'bg-gradient-to-r from-stone-50 via-stone-500 to-stone-950',
			animation: 'animate-ping'
		},
		{
			emote: '🐎',
			position: 0,
			color: 'bg-gradient-to-r from-blue-100 via-blue-300 to-blue-500',
			animation: 'bounce'
		},
		{
			emote: '🐎',
			position: 0,
			color: 'bg-gradient-to-r from-red-100 via-red-300 to-red-500',
			animation: 'bounce'
		},
		{
			emote: '🐎',
			position: 0,
			color: 'bg-gradient-to-r from-yellow-100 via-yellow-300 to-yellow-500',
			animation: 'bounce'
		},
		{
			emote: '🐎',
			position: 0,
			color: 'bg-gradient-to-r from-orange-100 via-orange-300 to-orange-500',
			animation: 'bounce'
		},
		{
			emote: '🐎',
			position: 0,
			color: 'bg-gradient-to-r from-teal-100 via-teal-300 to-teal-500',
			animation: 'bounce'
		},
		{
			emote: '🐎',
			position: 0,
			color: 'bg-gradient-to-r from-cyan-100 via-cyan-300 to-cyan-500',
			animation: 'bounce'
		},
		{
			emote: '🐎',
			position: 0,
			color: 'bg-gradient-to-r from-violet-100 via-violet-300 to-violet-500',
			animation: 'bounce'
		},
		{
			emote: '🐎',
			position: 0,
			color: 'bg-gradient-to-r from-rose-100 via-rose-300 to-rose-500',
			animation: 'bounce'
		},
		{
			emote: '🐎',
			position: 0,
			color: 'bg-gradient-to-r from-neutral-100 via-neutral-300 to-neutral-500',
			animation: 'bounce'
		}
	]);

	function progress() {
		let maxHorse = horses[0];
		for (let horse of horses) {
			let mult = 20;
			if (horse.emote == '🔲') {
				mult = 46;
			}
			let r = Math.random() * mult;
			horse.position += r;
			if (horse.position >= 100) {
				horse.position = 100;
			}

			if (horse.position > maxHorse.position) {
				maxHorse = horse;
			}
		}
		for (let horse of horses) {
			if (horse.position == maxHorse.position) {
				horse.animation = 'animate-spin';
			} else {
				horse.animation = 'bounce';
			}
		}
	}

	function reset() {
		for (let horse of horses) {
			horse.position = 0;
			horse.animation = 'bounce';
		}
	}
</script>

<div style="height: 1000px;" class="bg-green-400">
	<div class="py-5 text-center text-2xl font-bold">HORSE RACING GAME</div>
	<Button text={'Progress'} fn={progress} />
	<Button text={'Reset'} fn={reset} />
	<div class="py-10 pr-10">
		{#each horses as horse}
			<Horse
				emote={horse.emote}
				position={horse.position}
				color={horse.color}
				animation={horse.animation}
			/>
		{/each}
	</div>
</div>
