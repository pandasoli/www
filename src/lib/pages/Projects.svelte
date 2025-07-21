<script lang='ts'>
	import { onMount } from 'svelte'
	import { ProjectCard } from '$lib'

	let projectsPage: 'public'|'private' = $state('public')
	let clickSound: HTMLAudioElement

	onMount(() => {
		clickSound = new Audio('/click.mp3')
	})

	const changeProjectPage = (page: typeof projectsPage) => {
		clickSound.play()
		projectsPage = page
	}
</script>

<section class='flex flex-col gap-10'>
	<header class='text-center'>
		<h2 class='text-2xl'>my projects</h2>

		<div class='flex justify-center gap-2'>
			<button class='px-1 cursor-pointer {projectsPage === 'public' ? 'bg-green-300' : 'bg-gray-200'}' onclick={() => changeProjectPage('public')}>[public]</button>
			<button class='px-1 cursor-pointer {projectsPage === 'private' ? 'bg-green-300' : 'bg-gray-200'}' onclick={() => changeProjectPage('private')}>[private]</button>
		</div>

		{#if projectsPage === 'private'}
			<p class='border-l-2 broder-gray-600 pl-6 text-gray-600 mx-10 mt-6'>
				These projects different from the others are unique ideas that thus will
				be publicaly released open-source once finished their development.
			</p>
		{/if}
	</header>

	<div class='flex flex-wrap gap-8 px-10'>
		{#if projectsPage === 'public'}
			<ProjectCard
				url='https://github.com/pandasoli/bambloo'
				title='Bambloo'
				description='🎍🫧 | Build your own Discord activity'
			>
				<b>Bambloo</b> is a super easy web extension that lets you share what you're up
				to in your browser with your friends on Discord. It is straightforward,
				<u>configurable</u> and <code class='bg-gray-200 rounded px-1'>pretty</code> 🫐
			</ProjectCard>

			<ProjectCard
				url='https://codeberg.org/elisoli/pastel'
				title='pastel'
				description='🌮 | My lightweight task manager'
			>
				Pastel is an open-source, self-organizer task list CLI program I'm
				planning and making myself, and for myself use. All features and use
				cases are made based on my personal use and needs.
			</ProjectCard>

			<ProjectCard
				url='https://github.com/pandasoli/nekovim'
				title='NekoVIM'
				description='🐈‍⬛ | Most personalizable NeoVIM Discord Presence plugin'
			>
				Discord <a href='https://discord.com/rich-presence'>Rich Presence</a> plugin for <a href='https://neovim.io'>Neovim</a>
			</ProjectCard>

			<ProjectCard
				url='https://web-brainfuck.vercel.app'
				title='Web Brainf!@k'
				description='🧠 | Brainf*#k website'
			>
				The best site to learn and play with this programming language.<br>
				The most complete site for Brainf%.k study
			</ProjectCard>
		{:else if projectsPage === 'private'}
			<ProjectCard
				url=''
				title='sylpth 󱓇'
				description=''
			>
				A <strike>UTICL/I</strike> messaging program that uses P2P, <strike>dcnorne-r ttwpiyten onkora</strike> to
				communicate between devices without the need of a intermediary server.

				It shall support text messages and all kinds of binary documents. That
				might or not be displayed on the interface.
			</ProjectCard>

			<ProjectCard
				url=''
				title='N/I/H/I/L ☿'
				description=''
			>
				A simple and reliable Wayland composer that <strike>r esuo ettdeartng
				eiohc et sehu ehodsad aot endcwd f  dapetcro  in neatug res,neabto
				ldhe/sviaabel.</strike>
		</ProjectCard>

			<ProjectCard
				url=''
				title='coreutils'
				description=''
			>
				A re-implementation of the GNU coreutils that doesn't suck.
			</ProjectCard>
		{/if}
	</div>
</section>
