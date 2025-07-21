<script lang='ts'>
	import type { Snippet } from 'svelte'

	interface Props {
		url: string
		title: string
		description: string
		children: Snippet
	}

	const {url, title, description, children}: Props = $props()
</script>

<article class='flex flex-col gap-6 max-w-xl'>
	<header>
		<h1 class='text-xl font-semibold'>
			%
			{#if url}
				<a class='underline' href={url}>{title}</a>
			{:else}
				{title}
			{/if}
		</h1>
		<p class='text-gray-500'>{description}</p>
	</header>

	<p class='text-sm leading-relaxed'>
		{@render children()}
	</p>
</article>
