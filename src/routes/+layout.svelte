<script lang="ts">
	import '@skeletonlabs/skeleton/themes/theme-skeleton.css'
	import '@skeletonlabs/skeleton/styles/skeleton.css'
	import '../app.postcss'

	import { AppShell } from '@skeletonlabs/skeleton'

	import { Header, Footer } from '$lib/components'
</script>

<AppShell
	slotHeader="antialiased"
	slotPageContent="antialiased"
	slotPageFooter="card rounded-none p-2 flex justify-between items-center antialiased"
>
	<svelte:fragment slot="header">
		<Header />
	</svelte:fragment>

	<slot />

	<svelte:fragment slot="pageFooter">
		<Footer />
	</svelte:fragment>
</AppShell>
