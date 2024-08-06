<script>
	export let data;
	let copytext = 'copy';
</script>

<table class="table table-hover table-striped">
	<thead>
		<tr>
			<th scope="col">#</th>
			<th scope="col">Nik</th>
			<th scope="col">Nama</th>
			<th scope="col">ALamat</th>
		</tr>
	</thead>
	<tbody>
		{#each data as item}
			<tr>
				<th scope="row">{item.id}</th>
				<td
					>{item.nik}
					<button
						class="btn btn-sm btn-primary"
						on:click={() => {
							navigator.clipboard.writeText(item.nik);
							document.execCommand('copy');
						}}
					>
						{copytext}
					</button>
				</td>
				<td>{item.nama}</td>
				<td>{item.alamat}</td>
			</tr>
		{/each}
	</tbody>
</table>
