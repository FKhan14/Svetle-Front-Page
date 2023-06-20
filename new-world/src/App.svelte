<script>
	import data from './demo-output.json';
	/*function addRow() {
		data = [...data, [...newRow]]
		newRow = columns
	}
	function deleteRow(rowToBeDeleted) {
		data = data.filter(row => row != rowToBeDeleted)
	} */
	console.log(data);
	let columns = ["VMName", "IP", "HostName", "Status", "LastCheckInTime", "HyperVisor"]
	let newRow = [...columns];
	


	// possible solution 1
	//let vmname = document.getElementById(vm)
</script>
<!--{#each demo as demo(demo.IP)}
		<h1 class="extended" id = "vm">Virtual Machine: {demo.VMName}</h1>
		<h2 class= "extended">Status: {demo.Status}</h2>
		<h3 class="extended">Hyper Visor: {demo.HyperVisor}</h3>
		<h3 class="extended">Host: {demo.HostName}</h3>
		<h3 class="extended">last check in time: {demo.LastCheckInTime}</h3>
		<h3 class="extended">IP: {demo.IP}</h3>
	{/each} -->
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
			<!--<button on:click={() => deleteRow(row)}>X</button>-->
		</tr>
	{/each}
	<tr style="color: grey">
		{#each newRow as column}
			<td contenteditable="true" bind:innerHTML={column} />
		{/each}
		<!--<button on:click={addRow}>add</button>-->
	</tr>
	<!--<pre style="background: #eee">{JSON.stringify(data, null, 2)}</pre> -->
</table>

<style>
	tr td:focus {
		background: #eee;
	}
</style>