<script>
	import Button from '../../components/Button.svelte';
</script>

<div class="w-full bg-blue-300">
	<div class="prose p-5">
		<h1 class="text-center">Ryan's Profile</h1>

		<hr />

		<div
			class="profile-image h-20 w-20 overflow-hidden rounded-full bg-black bg-cover
     bg-center"
		></div>
		<div>Ryan Kim</div>
		<div>Student</div>
		<h2>About Me</h2>

		<p>Hi my name is Ryan.</p>

		<h2>Haiku Excercise</h2>
		<div class="bg-red-200 text-center">Crisp winds brush my face</div>
		<div class="bg-green-300 text-center">Golden leaves dance through the air</div>
		<div class="bg-yellow-400 text-center">Whispers of cold dawn</div>

		<h2>Components</h2>

		<Button text={'Click Me'} message={'I was clicked.'} />
		<Button text={'Dont Click Me'} message={'Why did you click me?'} />
	</div>
</div>

<style>
	.profile-image {
		background-image: url('https://images.unsplash.com/photo-1753872931676-79eaad94a36b?q=80&w=687&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D');
	}
</style>
