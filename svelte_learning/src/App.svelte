<script>
	export let name, age;

	//Contact Card Component
	import ContactCard from './ContactCard.svelte'

	//assign variable using reactive statements
	$: uppercaseName = name.toUpperCase();

	// increment age function
	const incrementAge = () => age++

	//change name
	const changeName = () => name === 'Taja'? name = 'LadyLotus': name = 'Taja'
	
	//input name function
	const nameInput = (e) => {
		e.preventDefault()
		name = e.target.value
	}

	//Use reactive variables to console.log to view state
	$: console.log('name',name)
	$: console.log('age',age)

</script>

<style>
	h1{
		color: purple;
	}

	button{
		color:yellow;
		border-radius: 8%;
		background-color: cornflowerblue;
	}
</style>

<!-- Contact Card -->
<ContactCard username = {name}/>

<main>
	<h1>Hello {uppercaseName}! I am a {age} year old.</h1>
	<button on:click="{incrementAge}"> Change the age</button>
	<button on:click="{changeName}">Change Name</button>
	<!-- <input type="text" value="{name}" on:input="{nameInput}"> -->
	<input type="text" bind:value="{name}">

</main>

