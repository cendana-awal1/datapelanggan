<script>
	import data from '../lib/data.json';
	import TablePelanggan from '../lib/TablePelanggan.svelte';
	let searchTerm = '';
	let dataPelanggan = [];

	const searchPelanggan = () => {
		dataPelanggan = data.filter((item) =>
			item.nama.toLowerCase().includes(searchTerm.toLowerCase())
		);
		console.log(dataPelanggan);
	};
</script>

<div class="container">
	<div class="row justify-content-center">
		<div class="col-md-10">
			<div>
				<h1 class="text-center">Data Pelanggan LPG</h1>
			</div>
			<div class="py-3 mb-3">
				<input
					type="text"
					class="form-control"
					placeholder="Cari Pelanggan"
					bind:value={searchTerm}
					aria-label="Cari Pelanggan"
					on:input={searchPelanggan}
				/>
			</div>
            <div class="table-responsive">

                <TablePelanggan data={dataPelanggan.length > 0 ? dataPelanggan : data} />
            </div>
		</div>
	</div>
</div>
