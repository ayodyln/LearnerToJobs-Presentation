<script lang="ts">
	export let slideNum: number, paginate: (num: number) => void
</script>

<div class="w-fit max-w-[1400px] flex items-center gap-4 card overflow-hidden">
	<button
		on:click={() => {
			paginate(slideNum - 1)
		}}
		class="fill-current btn btn-sm variant-filled rounded-none"
	>
		<span class="icon">
			<svg xmlns="http://www.w3.org/2000/svg" class="w-4" viewBox="0 0 448 512">
				<!--! Font Awesome Pro 6.4.0 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2023 Fonticons, Inc. -->
				<defs>
					<style>
						.fa-secondary {
							opacity: 0.4;
						}
					</style>
				</defs>
				<path
					class="fa-primary"
					d="M224 192h0V96c0-12.9-7.8-24.6-19.8-29.6s-25.7-2.2-34.9 6.9l-160 160c-12.5 12.5-12.5 32.8 0 45.3l160 160c9.2 9.2 22.9 11.9 34.9 6.9s19.8-16.6 19.8-29.6V320h0V192z"
				/>
				<path
					class="fa-secondary"
					d="M224 320V192H408c22.1 0 40 17.9 40 40v48c0 22.1-17.9 40-40 40l-184 0z"
				/>
			</svg>
		</span>
	</button>

	<span class="font-bold h4">{slideNum + 1}</span>

	<button
		on:click={() => {
			paginate(slideNum + 1)
		}}
		class="fill-current btn btn-sm variant-filled rounded-none"
	>
		<span class="icon">
			<svg xmlns="http://www.w3.org/2000/svg" class="w-4" viewBox="0 0 448 512">
				<!--! Font Awesome Pro 6.4.0 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2023 Fonticons, Inc. -->
				<defs>
					<style>
						.fa-secondary {
							opacity: 0.4;
						}
					</style>
				</defs>
				<path
					class="fa-primary"
					d="M224 320h0l0 96c0 12.9 7.8 24.6 19.8 29.6s25.7 2.2 34.9-6.9l160-160c12.5-12.5 12.5-32.8 0-45.3l-160-160c-9.2-9.2-22.9-11.9-34.9-6.9s-19.8 16.6-19.8 29.6l0 96h0V320z"
				/>
				<path
					class="fa-secondary"
					d="M224 192V320L40 320c-22.1 0-40-17.9-40-40V232c0-22.1 17.9-40 40-40H224z"
				/>
			</svg>
		</span>
	</button>
</div>
