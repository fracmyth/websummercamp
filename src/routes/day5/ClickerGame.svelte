<script>
	import { onMount } from 'svelte';
	import Button from '../../components/Button.svelte';
	let points = $state(50000000);
	let clickingPower = $state(1);
	let passiveIncome = $state(0);
	let goldenCookie = $state(0);
	let bloodCookie = $state(0);

	let upgradeClickCost = 500;
	let upgradePassiveCost = 2500;
	onMount(() => {
		// INTERVAL
		let passiveTimer = setInterval(() => {
			points += passiveIncome;
		}, 1000);

		let goldenTimer = setInterval(() => {
			if (Math.random() >= 0.9) {
				goldenCookie = 1;
			} else {
				goldenCookie = 0;
			}
		}, 10000);

		let bloodTimer = setInterval(() => {
			if (Math.random() >= 0.9) {
				bloodCookie = 1;
			} else {
				bloodCookie = 0;
			}
		}, 10000);

		return () => clearInterval(passiveTimer);
	});

	function increment() {
		let mult = 1;
		if (goldenCookie) {
			mult *= 777;
		}
		if (bloodCookie) {
			mult *= 7777;
		}
		points += clickingPower * mult;
	}

	function upgradeClickingPower(amount) {
		if (points - amount * upgradeClickCost >= 0) {
			points -= amount * upgradeClickCost;
			clickingPower += amount;
		}
	}

	function upgradePassiveIncome(amount) {
		if (points - amount * upgradePassiveCost >= 0) {
			points -= amount * upgradePassiveCost;
			passiveIncome += amount;
		}
	}
</script>

<!-- container for game -->
<div class="flex h-screen flex-col items-center justify-center bg-blue-200">
	<div>{points}</div>
	<div class="flex h-10 w-full justify-start">
		<div class="px-2 font-bold {goldenCookie === 1 ? '' : 'hidden'} text-amber-300">
			Golden Cookie: Power x777
		</div>
		<div class="px-2 font-bold {bloodCookie === 1 ? '' : 'hidden'} text-red-700">
			Blood Cookie: Power x7777
		</div>
	</div>
	<div
		onclick={increment}
		class="relative h-48 w-48 rounded-full bg-yellow-800 transition-all duration-100 active:scale-110"
	>
		<div class="absolute top-10 left-10 h-4 w-4 rounded-full bg-black"></div>
		<div class="absolute top-15 right-7 h-4 w-4 rounded-full bg-black"></div>
		<div class="absolute right-9 bottom-15 h-4 w-4 rounded-full bg-black"></div>
		<div class="absolute top-17 left-25 h-4 w-4 rounded-full bg-black"></div>
		<div class="absolute bottom-5 left-12 h-4 w-4 rounded-full bg-black"></div>
		<div class="absolute bottom-18 left-9 h-4 w-4 rounded-full bg-black"></div>
	</div>
	<div class="flex w-full border text-center">
		<div class="flex w-1/2 flex-col">
			<div>Click Upgrades</div>
			<Button text="+1 - {1 * upgradeClickCost}" fn={() => upgradeClickingPower(1)} />
			<Button text="+5 - {5 * upgradeClickCost}" fn={() => upgradeClickingPower(5)} />
			<Button text="+10 - {10 * upgradeClickCost}" fn={() => upgradeClickingPower(10)} />
			<Button text="+25 - {25 * upgradeClickCost}" fn={() => upgradeClickingPower(25)} />
			<Button text="+50 - {50 * upgradeClickCost}" fn={() => upgradeClickingPower(50)} />
			<Button text="+100 - {100 * upgradeClickCost}" fn={() => upgradeClickingPower(100)} />
		</div>
		<div class="flex w-1/2 flex-col">
			<div>Passive Upgrades</div>
			<Button text="+1 - {1 * upgradePassiveCost}" fn={() => upgradePassiveIncome(1)} />
			<Button text="+5 - {5 * upgradePassiveCost}" fn={() => upgradePassiveIncome(5)} />
			<Button text="+10 - {10 * upgradePassiveCost}" fn={() => upgradePassiveIncome(10)} />
			<Button text="+25 - {25 * upgradePassiveCost}" fn={() => upgradePassiveIncome(25)} />
			<Button text="+50 - {50 * upgradePassiveCost}" fn={() => upgradePassiveIncome(50)} />
			<Button text="+100 - {100 * upgradePassiveCost}" fn={() => upgradePassiveIncome(100)} />
		</div>
	</div>
</div>
