<script lang="ts">
	import { page } from '$app/stores';

	const id = $derived(Number($page.params.id));

	const colors = [
		'#e74c3c', '#3498db', '#2ecc71', '#f39c12', '#9b59b6',
		'#1abc9c', '#e67e22', '#2c3e50', '#c0392b', '#27ae60',
		'#8e44ad', '#d35400', '#16a085', '#f1c40f', '#7f8c8d',
	];

	const pages = Array.from({ length: 20 }, (_, i) => ({
		num: i + 1,
		color: colors[(id + i) % colors.length]
	}));
</script>

<div class="reader">
	<a class="back" href="/">Back to list</a>

	{#each pages as p}
		<div class="comic-page" style="background-color: {p.color};">
			<span class="page-label">Page {p.num}</span>
		</div>
	{/each}

	<a class="back" href="/">Back to list</a>
</div>

<style>
	.reader {
		padding-top: env(safe-area-inset-top);
		margin: 0;
	}

	.back {
		display: block;
		padding: 12px 16px;
		font-size: 16px;
		color: #007aff;
		text-decoration: none;
	}

	.comic-page {
		width: 100%;
		height: 800px;
		display: flex;
		align-items: center;
		justify-content: center;
	}

	.page-label {
		font-size: 48px;
		font-weight: 700;
		color: rgba(255, 255, 255, 0.8);
		text-shadow: 0 2px 4px rgba(0, 0, 0, 0.3);
	}
</style>
