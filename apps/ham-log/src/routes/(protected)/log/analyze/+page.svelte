<script lang="ts">
	import LogbookSelect from '$lib/components/logbook-select.svelte';
	import BandFix from './band-fix.svelte';
	import ContFix from './cont-fix.svelte';
	import DxccFix from './dxcc-fix.svelte';

	let state: 'ready' | 'start' = $state('ready');
</script>

<div class="flex flex-col gap-8">
	<h1 class="text-3xl">Analyze logbook</h1>

	{#if state === 'ready'}
		<div class="flex flex-col gap-4 md:flex-row md:items-end">
			<LogbookSelect class="w-full max-w-xs" />

			<button class="btn btn-primary" onclick={() => (state = 'start')}>Analyze</button>
		</div>
	{:else if state === 'start'}
		<div class="flex flex-col gap-4">
			<h3 class="text-xl">Missing DXCC entities</h3>

			<DxccFix />
		</div>

		<div class="flex flex-col gap-4">
			<h3 class="text-xl">Missing continents</h3>

			<ContFix />
		</div>

		<div class="flex flex-col gap-4">
			<h3 class="text-xl">Missing bands</h3>

			<BandFix />
		</div>
	{/if}
</div>
