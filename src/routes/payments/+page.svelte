<script lang="ts">
	import DataTable from './data-table.svelte';
	// tableName
	export let tableName: String;

	const toggleName = () => {
		if (tableName === 'world') {
			tableName = 'svelte';
		} else {
			tableName = 'world';
		}
	};
</script>

<div class="container mx-auto py-10">
	<div>DataTable: {tableName}</div>
	<button on:click={toggleName}>Toggle name</button>
	<DataTable />
</div>
