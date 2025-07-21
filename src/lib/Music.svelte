<script lang='ts'>
	import { onMount } from 'svelte'

	let audio: HTMLAudioElement
	let grapth = $state('<>')
	let grapthIndex = 0
	const graphStates = [ 'o', '(o)', '( o )' ]
	let musicTimer: number|null = null

	onMount(() => {
		audio = new Audio('/music.mp3')
		audio.loop = true
		audio.volume = 0.2
	})

	const musicLoop = () => {
		grapth = graphStates[grapthIndex]
		grapthIndex = (grapthIndex + 1) % 3
	}

	const startMusic = async () => {
		audio.play()
		musicLoop()
		musicTimer = setInterval(musicLoop, 500)
	}

	const stopMusic = () => {
		if (musicTimer) clearInterval(musicTimer)
		musicTimer = null
		grapthIndex = 0
		grapth = '<>'
		audio.pause()
	}

	const onclick = () => {
		if (musicTimer) stopMusic()
		else startMusic()
	}
</script>

<div class='fixed right-0 bottom-0 z-2'>
	<button {onclick} class='w-20 h-20 grid place-items-center cursor-pointer'>
		{grapth}
	</button>
</div>
