<script>
	export let name, age;

	// increment age function
	const incrementAge = () => age++
</script>

<main>
	<h1>Hello {name}! I am {age} years old.</h1>
	<button on:click="{incrementAge}"> Change the age</button>
</main>

<style>
h1{
	color: purple;
}
</style>