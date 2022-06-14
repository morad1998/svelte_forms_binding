<script>
	
const formValues = {name: ' ',
					profilesummary: ' ', 
					country:' ', 
					joblocation: ['Saudi Arabia'], 
					remoteWork: false, 
					skillSet:[],
					yearsOfExperience: ' ',
				}

let count = 0;

function eventCount(event){

	console.log(event);
	count++;

}

function submitForm(event){

	event.preventDefault();
	console.log(formValues);

}
	
</script>

<main>
	<div>
		<pre>
			{JSON.stringify(formValues,null,2)}
			
		</pre>
	
	</div>
	
	<form on:submit={submitForm}>
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

		<div>
			<input type="checkbox" id='remoteWork' bind:checked={formValues.remoteWork} >
			<label for="remoteWork"> Open to Remote Work</label>
		</div>

		<div>
			<label for="skillSet">Skill Set: </label>

			<input type="checkbox" id="html" value="html" bind:group={formValues.skillSet}>
			<label for="skillSet" >HTML</label>

			<input type="checkbox" id="CSS" value="css" bind:group={formValues.skillSet}>
			<label for="skillSet">CSS</label>

			<input type="checkbox" id="JAVASCRIPT" value="JavaScript" bind:group={formValues.skillSet}>
			<label for="skillSet">JAVASCRIPT</label>
		</div>

		<div>
			<label for="yearsOfExperience">Years of Experience: </label>

			<input type="radio" id="0-2" value="0-2" bind:group={formValues.yearsOfExperience}>
			<label for="yearsOfExperience">0-2</label>

			<input type="radio" id="3-4" value="3-4" bind:group={formValues.yearsOfExperience}>
			<label for="yearsOfExperience">3-4</label>

			<input type="radio" id="5-7" value="5-7" bind:group={formValues.yearsOfExperience}>
			<label for="5-7">5-7</label>

			<input type="radio" id="7-9" value="7-9" bind:group={formValues.yearsOfExperience}>
			<label for="7-9">7-9</label>

			<input type="radio" id="10+" value="10+" bind:group={formValues.yearsOfExperience}>
			<label for="yearsOfExperience">10+</label>
		</div>

		<div>
			<button >Submit</button>
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