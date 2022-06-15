<script>
	let fname = 'Morad';
	let lname = 'Alshammari';

	$: fullname = `${fname} ${lname}`;

	let items = [{id:1,title:'TV',price:100},{id:1,title:'phone',price:200},{id:1,title:'laptop',price:300},];
	$: total = items.reduce((total, curr)=>(total = total+curr.price),0)
	$: console.log(`Fullname is ${fname} ${lname}`);

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
	<button on:click={()=>{
		fname = 'Mohammad';
		lname = 'Morad';
	}}>Change name</button>
	<div>{fullname}</div>
	<div>{fname} {lname}</div>
	<button on:click={()=> {items = [...items, {id: 4, title: 'Mouse',price: 10}]}}>Add Item</button>
	<div>total - {total}</div>
	<div>
		<pre>
			{JSON.stringify(formValues,null,2)}
			
		</pre>
	
	</div>

	<div>
		<pre>
			{JSON.stringify(items,null,2)}
			
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