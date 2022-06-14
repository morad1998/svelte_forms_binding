<script>
	
const formValues = {name: ' ',profilesummary: ' ', country:' ', joblocation: ['Saudi Arabia'],}

let count = 0;

function eventCount(event){

	console.log(event);
	count++;

}
	
</script>

<main>
	<div>
		<pre>
			{JSON.stringify(formValues,null,2)}
			
		</pre>
	
	</div>
	
	<form >
		<div>
			<label for="name">Name</label>
			<input type="text" id="name" bind:value={formValues.name}/>
		</div>
		<div>
			<label for="profile">Profile Summary: </label>
			<textarea id="profile" bind:value={formValues.profilesummary}/>
		</div>

		<div>
			<label for="profile">Country: </label>
			<select id="country" bind:value={formValues.country}>
				<option value="">Select Country</option>
				<option value="Saudi Arabia">Saudi Arabia</option>
				<option value="Bahrain">Bahrain</option>
				<option value="UAE">UAE</option>
			</select>
		</div>

		<div>
			<label for="job-location">job-location: </label>
			<select id="job-location" bind:value={formValues.joblocation} multiple>
				<option value="">Select Country</option>
				<option value="Saudi Arabia">Saudi Arabia</option>
				<option value="Bahrain">Bahrain</option>
				<option value="UAE">UAE</option>
			
			</select>

		</div>


	</form>
	<div>
		<p>{count}</p>
		<button on:click={eventCount}>Click</button>
	</div>
	

</main>
	

<style>

input+label{
	display: inline-flex;
}


main{

	padding: 1em;
	max-width: 240px;
	margin: 0 auto;
}

	h1 {
		color: #6b81ec;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	
</style>