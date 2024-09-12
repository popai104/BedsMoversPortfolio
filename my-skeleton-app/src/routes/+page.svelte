<script>
	import Background from "../components/animatedbg_scrollingtext.svelte";
	import Text from "../components/Typewritertext.svelte";
</script>

<div id="homepage" class="container h-full mx-auto flex justify-center items-center flex-col p-6">
	<Background />
	<div id="Typewriter_text" class="md:w-4/6 mr-auto padding">
		<Text />
	</div>
</div>

<style lang="scss">
	.padding {
		padding-top: calc(2vw + 1vh);
	}
																							

</style>
