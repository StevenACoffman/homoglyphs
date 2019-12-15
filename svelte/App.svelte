<script>
	export let name;
</script>

<style>
	h1 {
		color: purple;
	}
</style>

<input bind:value={name}>

<h1>Hello, {name}!</h1>
