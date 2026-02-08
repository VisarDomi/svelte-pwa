<script lang="ts">
	const items = Array.from({ length: 80 }, (_, i) => ({
		id: i + 1,
		title: `Chapter ${i + 1}`,
		excerpt: [
			'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.',
			'Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.',
			'Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.',
			'Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.',
			'Curabitur pretium tincidunt lacus. Nulla gravida orci a odio. Nullam varius, turpis et commodo pharetra.',
			'Praesent dapibus, neque id cursus faucibus, tortor neque egestas augue, eu vulputate magna eros eu erat.',
			'Aliquam erat volutpat. Nam dui mi, tincidunt quis, accumsan porttitor, facilisis luctus, metus.',
			'Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas.',
		][i % 8]
	}));
</script>

<div class="list">
	{#each items as item}
		<a class="list-item" href="/item/{item.id}">
			<span class="item-id">#{item.id}</span>
			<div class="item-content">
				<h2>{item.title}</h2>
				<p>{item.excerpt}</p>
			</div>
		</a>
	{/each}
</div>

<style>
	.list {
		padding: 0;
		margin: 0;
	}

	.list-item {
		display: flex;
		align-items: flex-start;
		gap: 12px;
		padding: 16px;
		border-bottom: 1px solid #e0e0e0;
		text-decoration: none;
		color: inherit;
		-webkit-tap-highlight-color: rgba(0, 0, 0, 0.05);
	}

	.list-item:active {
		background: #f0f0f0;
	}

	.item-id {
		flex-shrink: 0;
		font-size: 14px;
		font-weight: 600;
		color: #888;
		padding-top: 2px;
		min-width: 36px;
	}

	.item-content {
		min-width: 0;
	}

	h2 {
		margin: 0 0 4px 0;
		font-size: 17px;
		font-weight: 600;
	}

	p {
		margin: 0;
		font-size: 14px;
		color: #666;
		line-height: 1.4;
	}
</style>
