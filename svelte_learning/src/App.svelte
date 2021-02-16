<script>
	export let name, age;

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

<main>
	<h1>Hello {uppercaseName}! I am {age} years old.</h1>
	<button on:click="{incrementAge}"> Change the age</button>
	<button on:click="{changeName}">Change Name</button>
	<input type="text" value="{name}" on:input="{nameInput}">
</main>

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