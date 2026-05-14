<script>
	// @ts-nocheck
	import { flip } from 'svelte/animate';
	import { dndzone, TRIGGERS } from 'svelte-dnd-action';
	import { addFieldGroup, reorderFieldGroups } from '$lib/store.js';
	import TripFieldGroupSection from './TripFieldGroupSection.svelte';

	export let trip;

	$: localGroups = [...(trip?.arr_field_groups ?? [])]
		.sort((a, b) => a.int_order - b.int_order)
		.map((group) => ({ ...group, id: group.int_id }));

	let groupsDragDisabled = true;
	let newGroupName = '';

	async function handleAddGroup() {
		if (!newGroupName.trim()) return;
		await addFieldGroup(newGroupName.trim());
		newGroupName = '';
	}

	function handleGroupsDndConsider(e) {
		localGroups = e.detail.items;
		if (e.detail.info.trigger === TRIGGERS.DRAG_STOPPED) groupsDragDisabled = true;
	}

	function handleGroupsDndFinalize(e) {
		localGroups = e.detail.items;
		reorderFieldGroups(localGroups.map((group) => group.int_id));
		groupsDragDisabled = true;
	}
</script>

<section class="trip-fields" aria-labelledby="trip-fields-title">
	<div class="trip-fields-header">
		<h2 id="trip-fields-title">Trip Fields</h2>
	</div>

	<div class="add-group-row">
		<input
			type="text"
			bind:value={newGroupName}
			placeholder="Group name (e.g., Hotel)"
			on:keydown={(e) => e.key === 'Enter' && handleAddGroup()}
		/>
		<button on:click={handleAddGroup}>Add Group</button>
	</div>

	{#if localGroups.length > 0}
		<div
			class="field-group-list"
			use:dndzone={{ items: localGroups, flipDurationMs: 200, dragDisabled: groupsDragDisabled }}
			on:consider={handleGroupsDndConsider}
			on:finalize={handleGroupsDndFinalize}
		>
			{#each localGroups as group (group.id)}
				<div class="field-group-dnd-row" animate:flip={{ duration: 200 }}>
					<span
						role="button"
						tabindex="-1"
						aria-label="Drag to reorder"
						class="group-drag-handle"
						on:mousedown={() => (groupsDragDisabled = false)}
						on:touchstart|preventDefault={() => (groupsDragDisabled = false)}
					>⠿</span>
					<div class="field-group-content">
						<TripFieldGroupSection {group} fields={trip.arr_fields ?? []} />
					</div>
				</div>
			{/each}
		</div>
	{:else}
		<p class="empty-fields">No trip fields yet.</p>
	{/if}
</section>

<style>
	.trip-fields {
		margin-top: 2rem;
		padding-top: 1.25rem;
		border-top: 1px solid var(--color-border-light);
	}

	.trip-fields-header {
		margin-bottom: 0.75rem;
	}

	.trip-fields h2 {
		margin: 0;
		font-size: 1.1rem;
		color: var(--color-text);
	}

	.add-group-row {
		display: flex;
		gap: 0.5rem;
		margin-bottom: 1rem;
	}

	.add-group-row input {
		flex: 1;
		min-width: 0;
		padding: 0.5rem;
		border: 1px solid var(--color-border);
		border-radius: 4px;
		font-size: 0.9rem;
	}

	button {
		padding: 0.4rem 0.9rem;
		cursor: pointer;
		border: 1px solid var(--color-border);
		background: var(--color-btn-bg);
		border-radius: 4px;
		font-size: 0.875rem;
		white-space: nowrap;
	}

	button:hover {
		background: var(--color-btn-hover);
	}

	.field-group-list {
		display: flex;
		flex-direction: column;
		gap: 0;
		outline: none;
	}

	.field-group-dnd-row {
		display: flex;
		align-items: flex-start;
	}

	.group-drag-handle {
		padding-top: 1rem;
		padding-right: 0.25rem;
		color: var(--color-text-faint);
		cursor: grab;
		font-size: 1rem;
		flex-shrink: 0;
		touch-action: none;
		user-select: none;
	}

	.group-drag-handle:active {
		cursor: grabbing;
	}

	.field-group-content {
		flex: 1;
		min-width: 0;
	}

	.empty-fields {
		color: var(--color-text-faint);
		font-style: italic;
		margin: 0;
	}

	@media (max-width: 480px) {
		.add-group-row {
			flex-direction: column;
		}
	}
</style>
