<script lang='ts'>
	import { Aside, Music, Footer } from '$lib'
	import { ProjectsPage, LinuxJourneyPage } from '$lib/pages'
	import '../app.css'

	let { children } = $props()

	const pages = [
		'main',
		'projects',
		'linux-journey'
	] as const

	type Page = typeof pages[number]
	let page: Page = $state('main')

	const changePage = (n: Page) => page = n
</script>

<svelte:head>
	<title>EliSoli();</title>
</svelte:head>

<div class='min-h-screen flex flex-col'>
	<div class='flex-1 min-h-screen flex flex-col md:flex-row gap-8 pt-8 mb-50'>
		<Aside entries={[...pages]} focus={page} update={changePage} />

		{#if page === 'main'}
			<div>
				{@render children()}
			</div>
		{:else if page === 'projects'}
			<ProjectsPage />
		{:else if page === 'linux-journey'}
			<LinuxJourneyPage />
		{/if}
	</div>

	<Music />
	<Footer />
</div>
