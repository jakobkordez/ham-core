<script lang="ts">
	import LogbookSelect from '$lib/components/logbook-select.svelte';
	import QsoList from './qso-list.svelte';
	import QsoForm from './qso-form.svelte';
	import Filters from './filters.svelte';
	import Pagination from './pagination.svelte';
	import Selection from './selection.svelte';
	import Fa from 'svelte-fa';
	import { faCog } from '@fortawesome/free-solid-svg-icons';
	import LogMap from './log-map.svelte';
	import WsjtButton from '$lib/components/wsjt-button.svelte';
</script>

<div class="mx-auto flex max-w-5xl flex-col gap-10">
	<div>
		<div class="flex flex-wrap items-end justify-between gap-4">
			<LogbookSelect />

			<div class="flex flex-wrap gap-3">
				<a href="/log/map" class="btn btn-sm">Map</a>
				<a href="/log/adif-import" class="btn btn-sm">Import ADI</a>
				<a href="/log/settings" class="btn btn-sm">
					<Fa icon={faCog} />
					<span>Settings</span>
				</a>
			</div>
		</div>

		<div class="flex justify-end gap-4">
			<WsjtButton />
		</div>
	</div>

	<div class="flex flex-col gap-6 lg:flex-row lg:items-start [&>*]:flex-1">
		<QsoForm />

		<LogMap />
	</div>

	<div class="flex w-full flex-col gap-4">
		<Filters />

		<Pagination />

		<QsoList />

		<Selection />
	</div>
</div>
