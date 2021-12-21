<script>
	let myActivitys;

	async function getBoredActivity() {
		let res = await fetch('https://www.boredapi.com/api/activity');
		let data = await res.json();
		
		myActivitys = data.activity;
	}

	const handleClick = function() {
		getBoredActivity()
	}
</script>

<h1>Doing activities is importante click below to generate exercises</h1>

<button on:click={handleClick}>
	Generate activities
</button>

{#if myActivitys}
	<p>{myActivitys}</p>
{/if}

<style>
	h1 {
		text-align: center;
	}

	button {
		display: block;
		margin: 1rem auto;
		font-weight: bold;
		padding: 8px 12px;
	}

	p {
		text-align: center;
		background: red;
		border: 2px solid #000;
		padding: 8px 12px;
		font-weight: bold;
		text-transform: uppercase;
		color: white;
	}
</style>