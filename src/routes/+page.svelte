<script lang="ts">
	import Paginator from '../components/Paginator.svelte'
	import { TitleSlide, EndSlide } from '../components/slides'

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
</script>

<svelte:window on:keydown={slideHandler} />

<section
	id="presentation-container"
	class="h-full w-full flex flex-col items-center justify-center gap-2"
>
	<div id="slide" class="card p-8 aspect-video max-w-[1400px] w-full">
		{#each slides as slide, i}
			{#if slideNum === i}
				<svelte:component this={slide.comp} />
			{/if}
		{/each}
	</div>

	<Paginator {slideNum} />
</section>
