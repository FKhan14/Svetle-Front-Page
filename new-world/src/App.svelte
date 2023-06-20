<script>
	import data from './demo-output.json';
	
	console.log(data);
	let columns = ["VMName", "IP", "HostName", "Status", "LastCheckInTime", "HyperVisor"]
	let newRow = [...columns];


	// possible solution 1
	//let vmname = document.getElementById(vm)
</script>
<p>Hello Wrold</p>
<table>
	<tr>
		{#each columns as column}
			<th>{column}</th>
		{/each}
	</tr>
	
	{#each data as row}
		<tr>
			{#each row as cell}
			<td contenteditable="true" bind:innerHTML={cell} />
			{/each}
		
		</tr>
	{/each}
	<tr style="color: grey">
		{#each newRow as column}
			<td contenteditable="true" bind:innerHTML={column} />
		{/each}
		
	</tr>
	<pre style="background: #eee">{JSON.stringify(data, null, 2)}</pre> 
</table>

<style>
	tr td:focus {
		background: #eee;
	}
	table {
		display: block;
	}
</style>