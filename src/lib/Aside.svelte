<script lang='ts' generics='T extends string'>
	import { onMount } from 'svelte'

	interface Props<T> {
		entries: T[]
		focus: T
		update: (entry: T) => void
	}

	const { entries, focus, update }: Props<T> = $props()

	let clickSound: HTMLAudioElement

	onMount(() => {
		clickSound = new Audio('/click.mp3')
	})

	const onclick = (e: Event & { currentTarget: HTMLButtonElement }) => {
		clickSound.play()
		update(e.currentTarget.name as T)
	}
</script>

<aside class='px-4 md:px-0 pt-6 md:pt-0 md:pl-10'>
<pre class='font-semibold'>```sh
<span class='text-gray-600'>#!/bin/sh -e</span>
<span class='text-blue-400'>echo</span> <span class='text-green-400'>"<a href='https://github.com/pandasoli'>github.com/pandasoli</a>"</span>
<span class='text-blue-400'>echo</span> <span class='text-green-400'>"<a href='https://codeberg.org/elisoli'>codeberg.org/elisoli</a>"</span>
```</pre>

	<div class='my-4'></div>

	<nav>
		<ul class='flex justify-center md:flex-col gap-2'>
			{#each entries as entry}
				<li>
					<button
						name={entry}
						{onclick}
						class='px-1 cursor-pointer {entry === focus ? 'bg-green-300' : 'bg-gray-200'}'
					>[{entry}]</button>
				</li>
			{/each}
		</ul>
	</nav>
</aside>
