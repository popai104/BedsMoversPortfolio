<script>
	import Background from "../components/animatedbg_scrollingtext.svelte";
	import Text from "../components/Typewritertext.svelte";
	import Fire from "../components/burningfire.svelte";
</script>

<div id="homepage" class="container h-full mx-auto flex justify-center items-center flex-col p-6">
	<Background />
	<div id="Typewriter_text" class="md:w-4/6 mr-auto padding">
		<Text />
	</div>
	<div id="slide_in_card" class="md:w-2/6 ml-auto align-middle text-center slide-in">
		<div class="container1">
			<div class="card">
				<div class="face face1">
					<div class="content">
						<span class="stars"></span>
						<h2 class="java">Java</h2>
						<p class="java">Java is a class-based, object-oriented programming language that is designed to have as few implementation dependencies as possible.</p>
					</div>
				</div>
				<div class="face face2">
					<h2>01</h2>
				</div>
			</div>
			
			<div class="card">
				<div class="face face1">
					<div class="content">
						<span class="stars"></span>
						<h2 class="python">Python</h2>
						<p class="python">Python is an interpreted, high-level and general-purpose programming language.</p>
					</div>
				</div>
				<div class="face face2">
					<h2>02</h2>
				</div>
			</div>
			
			<div class="card">
				<div class="face face1">
					<div class="content">
						<span class="stars"></span>
						<h2 class="cSharp">C#</h2>
						<p class="cSharp">C# is a general-purpose, multi-paradigm programming language encompassing static typing, strong typing, lexically scoped and component-oriented programming disciplines.</p>
					</div>
				</div>
				<div class="face face2">
					<h2>03</h2>
				</div>
			</div>
		</div>
	</div>
</div>

<style lang="scss">
	.padding {
		padding-top: calc(2vw + 1vh);
	}
	
	@keyframes slide-in {
		0% {
			transform: translateX(100%);
			opacity: 0;
		}
		100% {
			transform: translateX(0);
			opacity: 1;
		}
	}
	
	.slide-in {
		transform: translateX(200%);
		animation: slide-in 0.7s ease-out 4.5s forwards;
	}
	
	.container1 {
		z-index: -1;
		display: grid;
		max-width: 300vw;
		grid-template-columns: 1fr;
		grid-gap: 35px 210px;
		margin: 0 auto;
		padding: 40px 0;
		.card {
			position: relative;
			width: 30vw;
			height: 400px;
			margin: 0 auto;
			background: #000;
			border-radius: 15px;
			box-shadow: 0 15px 60px rgba(0, 0, 0, 0.5);
			
			.face {
				position: absolute;
				bottom: 0;
				left: 0;
				width: 100%;
				height: 100%;
				display: flex;
				justify-content: center;
				align-items: center;
				
				&.face1 {
					box-sizing: border-box;
					padding: 20px;
					
					h2 {
						margin: 0;
						padding: 0;
					}
					
					.java {
						background-color: #ffffff;
						-webkit-background-clip: text;
						-webkit-text-fill-color: transparent;
					}
					
					.python {
						background-color: #ffffff;
						-webkit-background-clip: text;
						-webkit-text-fill-color: transparent;
					}
					
					.cSharp {
						background-color: #ffffff;
						-webkit-background-clip: text;
						-webkit-text-fill-color: transparent;
					}
				}
				
				&.face2 {
					transition: 0.5s;
					
					h2 {
						margin: 0;
						padding: 0;
						font-size: 10em;
						color: #fff;
						transition: 0.5s;
						text-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
						z-index: 10;
					}
				}
			}
		}
		
		.card:hover .face.face2 {
			height: 60px;
			
			h2 {
				font-size: 2em;
			}
		}
		
		.card:nth-child(1) .face.face2 {
			background-image: linear-gradient(
			40deg,
			#00000000 0,
			#d32929 45%,
			#ffffff52 100%
			);
			border-radius: 15px;
		}
		
		.card:nth-child(2) .face.face2 {
			background-image: linear-gradient(
			40deg,
			#00000079 0%,
			#532cbd 45%,
			#ffffff52 100%
			);
			border-radius: 15px;
		}
		
		.card:nth-child(3) .face.face2 {
			background-image: linear-gradient(
			40deg,
			#00000071 0%,
			#34d441ee 45%,
			#ffffff46 100%
			);
			border-radius: 15px;
		}
	}

	@media (max-width: 768px) {
		.container1 {
			grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
			grid-gap: 20px;
			padding: 20px 0;
			.card {
				width: 200px;
				height: 300px;
			}
		}
	}

	@media (max-width: 480px) {
		.container1 {
			grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
			grid-gap: 10px;
			padding: 10px 0;
			.card {
				width: 150px;
				height: 250px;
			}
		}
	}

</style>