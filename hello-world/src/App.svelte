<script>
	import demo from './demo-output.json';
	function display(){
		document.getElementByClass("extended")
			.style.display = "block";
	}
</script>
	{#each demo as demo(demo.IP)}
		<h1>Virtual Machine: {demo.VMName}</h1>
		<h2>Status: {demo.Status}</h2>
		<h3 class="extended">Hyper Visor: {demo.HyperVisor}</h3>
		<h3 class="extended">Host: {demo.HostName}</h3>
		<h3 class="extended">last check in time: {demo.LastCheckInTime}</h3>
	{/each}
	<button on:click{display}>show more</button>
<style>
	.extended{
		display: block;
	}
</style>