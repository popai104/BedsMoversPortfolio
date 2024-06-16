<script>
    import Background from "../components/animatedbg_scrollingtext.svelte";
	import Text from "../components/Typewritertext.svelte";
	import Fire from "../components/burningfire.svelte";
</script>

<div class="container h-full mx-auto flex justify-center items-center flex-col p-6">
	<Background />
	<div class="md:w-4/6 mr-auto padding">
		<Text />
	</div>
</div>

<style>
	.padding {
		padding-top: calc(2vw + 1vh);
		padding-bottom: calc(3vw + 1vh);
	}
</style>