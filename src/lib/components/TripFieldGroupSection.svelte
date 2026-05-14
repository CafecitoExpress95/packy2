<script>
	// @ts-nocheck
	import { flip } from 'svelte/animate';
	import { dndzone, TRIGGERS } from 'svelte-dnd-action';
	import {
		addField,
		deleteField,
		deleteFieldGroup,
		renameFieldGroup,
		reorderFields,
		updateField
	} from '$lib/store.js';

	export let group;
	export let fields;

	$: localFields = fields
		.filter((field) => field.int_group_id === group.int_id)
		.sort((a, b) => a.int_order - b.int_order)
		.map((field) => ({ ...field, id: field.int_id }));

	let fieldsDragDisabled = true;
	let newFieldLabel = '';

	function handleFieldsDndConsider(e) {
		localFields = e.detail.items;
		if (e.detail.info.trigger === TRIGGERS.DRAG_STOPPED) fieldsDragDisabled = true;
	}

	function handleFieldsDndFinalize(e) {
		localFields = e.detail.items;
		reorderFields(
			group.int_id,
			localFields.map((field) => field.int_id)
		);
		fieldsDragDisabled = true;
	}

	async function handleAddField() {
		if (!newFieldLabel.trim()) return;
		await addField(group.int_id, newFieldLabel);
		newFieldLabel = '';
	}

	async function handleRenameGroup(e) {
		const newName = e.currentTarget.value.trim();
		if (!newName || newName === group.str_name) {
			e.currentTarget.value = group.str_name;
			return;
		}
		await renameFieldGroup(group.int_id, newName);
	}

	async function handleDeleteGroup() {
		if (!confirm(`Delete "${group.str_name}" and all of its fields?`)) return;
		await deleteFieldGroup(group.int_id);
	}

	async function handleFieldChange(fieldId, fieldName, value) {
		await updateField(fieldId, { [fieldName]: value });
	}
</script>

<section class="field-group">
	<div class="field-group-header">
		<label class="sr-only" for={`fieldGroupName-${group.int_id}`}>Group name</label>
		<input
			id={`fieldGroupName-${group.int_id}`}
			class="group-name-input"
			type="text"
			value={group.str_name}
			placeholder="Group name"
			on:change={handleRenameGroup}
		/>
		<button class="danger-btn" on:click={handleDeleteGroup}>Delete Group</button>
	</div>

	<div class="add-field-row">
		<input
			type="text"
			bind:value={newFieldLabel}
			placeholder="Field label (e.g., Confirmation Number)"
			on:keydown={(e) => e.key === 'Enter' && handleAddField()}
		/>
		<button on:click={handleAddField}>Add Field</button>
	</div>

	{#if localFields.length > 0}
		<div
			class="field-list"
			use:dndzone={{ items: localFields, flipDurationMs: 200, dragDisabled: fieldsDragDisabled }}
			on:consider={handleFieldsDndConsider}
			on:finalize={handleFieldsDndFinalize}
		>
			{#each localFields as field (field.id)}
				<div class="field-row" animate:flip={{ duration: 200 }}>
					<span
						role="button"
						tabindex="-1"
						aria-label="Drag to reorder"
						class="drag-handle"
						on:mousedown={() => (fieldsDragDisabled = false)}
						on:touchstart|preventDefault={() => (fieldsDragDisabled = false)}
					>⠿</span>
					<label class="sr-only" for={`fieldLabel-${field.int_id}`}>Field label</label>
					<input
						id={`fieldLabel-${field.int_id}`}
						class="field-label-input"
						type="text"
						value={field.str_label}
						placeholder="Label"
						on:change={(e) => handleFieldChange(field.int_id, 'str_label', e.currentTarget.value)}
					/>
					<label class="sr-only" for={`fieldValue-${field.int_id}`}>Field value</label>
					<input
						id={`fieldValue-${field.int_id}`}
						class="field-value-input"
						type="text"
						value={field.str_value}
						placeholder="Value"
						on:change={(e) => handleFieldChange(field.int_id, 'str_value', e.currentTarget.value)}
					/>
					<button class="danger-btn compact-btn" on:click={() => deleteField(field.int_id)}>Delete</button>
				</div>
			{/each}
		</div>
	{:else}
		<p class="empty-fields">No fields yet.</p>
	{/if}
</section>

<style>
	.field-group {
		margin-bottom: 1rem;
		padding: 1rem;
		border: 1px solid var(--color-border);
		border-radius: 4px;
		background: var(--color-surface);
	}

	.field-group-header {
		display: flex;
		align-items: center;
		gap: 0.5rem;
		margin-bottom: 1rem;
	}

	.group-name-input {
		flex: 1;
		min-width: 0;
		padding: 0.45rem 0.5rem;
		border: 1px solid var(--color-border);
		border-radius: 4px;
		font-size: 1rem;
		font-weight: 600;
	}

	.add-field-row,
	.field-row {
		display: flex;
		align-items: center;
		gap: 0.5rem;
	}

	.add-field-row {
		margin-bottom: 0.75rem;
	}

	.add-field-row input,
	.field-row input {
		padding: 0.45rem 0.5rem;
		border: 1px solid var(--color-border);
		border-radius: 4px;
		font-size: 0.9rem;
	}

	.add-field-row input {
		flex: 1;
		min-width: 0;
	}

	.field-list {
		display: flex;
		flex-direction: column;
		gap: 0.45rem;
		outline: none;
	}

	.field-row {
		padding: 0.35rem 0;
		border-bottom: 1px solid var(--color-border-light);
	}

	.field-row:last-child {
		border-bottom: none;
	}

	.field-label-input {
		width: min(38%, 14rem);
		flex-shrink: 0;
	}

	.field-value-input {
		flex: 1;
		min-width: 0;
	}

	.drag-handle {
		color: var(--color-text-faint);
		cursor: grab;
		font-size: 1rem;
		flex-shrink: 0;
		touch-action: none;
		user-select: none;
	}

	.drag-handle:active {
		cursor: grabbing;
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

	.compact-btn {
		padding-inline: 0.55rem;
	}

	.danger-btn {
		border-color: var(--color-danger);
		color: var(--color-danger);
	}

	.danger-btn:hover {
		background: var(--color-danger-light);
	}

	.empty-fields {
		color: var(--color-text-faint);
		font-style: italic;
		margin: 0;
	}

	.sr-only {
		position: absolute;
		width: 1px;
		height: 1px;
		padding: 0;
		margin: -1px;
		overflow: hidden;
		clip: rect(0, 0, 0, 0);
		white-space: nowrap;
		border: 0;
	}

	@media (max-width: 640px) {
		.field-group {
			padding: 0.5rem;
		}

		.field-group-header,
		.add-field-row,
		.field-row {
			align-items: stretch;
		}

		.field-group-header,
		.add-field-row {
			flex-direction: column;
		}

		.field-row {
			display: grid;
			grid-template-columns: auto 1fr auto;
		}

		.field-label-input,
		.field-value-input {
			grid-column: 2 / 4;
			width: 100%;
		}

		.compact-btn {
			grid-column: 2 / 4;
		}
	}
</style>
