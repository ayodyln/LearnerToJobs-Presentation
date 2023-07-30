<script lang="ts">
	import Paginator from '../components/Paginator.svelte'
	import { TitleSlide, EndSlide } from '../components/slides'
	import { fade, type SlideParams } from 'svelte/transition'

	$: slideNum = 0

	const slides = [
		{ name: 'TitleSlide', comp: TitleSlide },
		{ name: 'EndTitle', comp: EndSlide }
	]

	const slideHandler = (e: KeyboardEvent) => {
		switch (e.key) {
			case 'ArrowRight':
				if (slideNum === slides.length - 1) return
				slideNum += 1
				break
			case 'ArrowLeft':
				if (slideNum === 0) return
				slideNum -= 1
				break
			case ' ':
				if (slideNum === slides.length - 1) return
				slideNum += 1
				break
			case 'Spacebar':
				if (slideNum === slides.length - 1) return
				slideNum += 1
				break
			default:
				break
		}
	}

	const paginate = (num: number) => {
		if (num < 0 || num > slides.length - 1) return
		slideNum = num
	}
</script>

<svelte:head>
	<title>Learner to Jobs Project Presentation</title>
	<meta
		name="description"
		content="UVU Senior Capstone group for the Learner to Jobs project's presentation for the first semester."
	/>
</svelte:head>

<svelte:window on:keydown={slideHandler} />

<section
	id="presentation-container"
	class="h-full w-full flex flex-col items-center justify-center gap-2"
>
	<div
		id="slide"
		class="card variant-filled before:rounded-xl aspect-video max-w-[1400px] w-full overflow-hidden rounded-xl"
	>
		{#each slides as slide, i}
			{#if slideNum === i}
				<div class="h-full w-full" in:fade={{ duration: 200 }}>
					<svelte:component this={slide.comp} />
				</div>
			{/if}
		{/each}
	</div>

	<Paginator {slideNum} {paginate} />
</section>
