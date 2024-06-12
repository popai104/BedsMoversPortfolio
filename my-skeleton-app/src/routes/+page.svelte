<!-- YOU CAN DELETE EVERYTHING IN THIS PAGE -->

<div class="container h-full mx-auto flex justify-center items-center">
	<div class="space-y-10 text-center flex flex-col items-center">
		<div class="container blur-sm opacity-35 overflow-hidden" id="code-sleep-repeat-textanimation">
			<div class="box overflow-hidden">
			  <span style="--i: 1">
				<i>CODE</i>
				SLEEP?
				<i>REPEAT</i>
			  </span>
			  <span style="--i: 2">
				<i>CODE</i>
				SLEEP?
				<i>REPEAT</i>
			  </span>
			  <span style="--i: 3">
				<i>CODE</i>
				SLEEP?
				<i>REPEAT</i>
			  </span>
			  <span style="--i: 4">
				<i>CODE</i>
				SLEEP?
				<i>REPEAT</i>
			  </span>
			  <span style="--i: 5">
				<i>CODE</i>
				SLEEP?
				<i>REPEAT</i>
			  </span>
			  <span style="--i: 6">
				<i>CODE</i>
				SLEEP?
				<i>REPEAT</i>
			  </span>
			  <span style="--i: 7">
				<i>CODE</i>
				SLEEP?
				<i>REPEAT</i>
			  </span>
			  <span style="--i: 8">
				<i>CODE</i>
				SLEEP?
				<i>REPEAT</i>
			  </span>
			  <span style="--i: 9">
				<i>CODE</i>
				SLEEP?
				<i>REPEAT</i>
			  </span>
			  <span style="--i: 10">
				<i>CODE</i>
				SLEEP?
				<i>REPEAT</i>
			  </span>
			  <span style="--i: 11">
				<i>CODE</i>
				SLEEP?
				<i>REPEAT</i>
			  </span>
			  <span style="--i: 12">
				<i>CODE</i>
				SLEEP?
				<i>REPEAT</i>
			  </span>
			  <span style="--i: 13">
				<i>CODE</i>
				SLEEP?
				<i>REPEAT</i>
			  </span>
			  <span style="--i: 14">
				<i>CODE</i>
				SLEEP?
				<i>REPEAT</i>
			  </span>
			  <span style="--i: 15">
				<i>CODE</i>
				SLEEP?
				<i>REPEAT</i>
			  </span>
			  <span style="--i: 16">
				<i>CODE</i>
				SLEEP?
				<i>REPEAT</i>
			  </span>
			</div>
		</div>

	</div>
</div>

<style lang="scss">
	@import url('https://fonts.googleapis.com/css2?family=Heebo:wght@400;600&family=Poppins:wght@100;500;600;800;900&family=Lobster+Two:ital,wght@0,400;0,700;1,400&display=swap');

$font1: 'Poppins', sans-serif;
$font2: 'Lobster Two', cursive;
$white:#d8c9c9;
$black:#000;
$primary-light: #f9fafb;
$second-light:#f0f0f0;
$third-light:#DADBDB;

$primary-dark:#222;
$second-grey:#4f4f4f;

$first-shadow: rgba(0,0,0,0.3);

$success: rgba(61, 168, 102, 0.6);
$error: rgba(168, 30, 14, 0.6);

$primary-color:#db2c2c;
$second-color:#8133c0;

/* GLOBAL CONFIG RESET */
* {
box-sizing: border-box;
margin: 0;
padding: 0;
padding-top: 80px;
font-family: $font1;
overflow: visible;
}

select:focus, input:focus, button:focus{
  outline:none;
}

/* -------- BODY DISPLAY --------- */
body {

background-color: $primary-dark;
overflow: clip;

display: flex;
  // flex-direction: column;
  justify-content: center;
  align-items: center;

min-height: 100vh;
}

/* -------- TYPE SELECTORS --------- */

/* -------- CLASS --------- */

.container{
  display: flex;
  justify-content: center;
  align-items: center;

  .box{
    transform-style: preserve-3d;
    animation: animate 7s ease-in-out infinite alternate;

    span{
      background: linear-gradient(90deg, rgba(0, 0, 0, 0.1), rgba(0, 0, 0, 0.5) 90%, transparent);
      text-transform: uppercase;
      line-height: 0.76em;
      position: absolute;
      color: $white;
      font-size: 3.5em;
      white-space: nowrap;
      font-weight: bold;
      padding: 0px 10px;
      transform-style: preserve-3d;
      text-shadow: 0 10px 15px $first-shadow;
      transform: translate(-50%, -50%) rotateX(calc(var(--i) * 22.5deg)) translateZ(109px);

      i{
        font-style: initial;

        &:nth-child(1){
          color: $primary-color;
        }

        &:nth-child(2){
          color: $second-color;
        }
      }
    }
  }
}

@keyframes animate {
  0%{
    transform: perspective(500px) rotateX(0deg) rotate(5deg);
  }
  100%{
    transform: perspective(50px) rotateX(360deg) rotate(5deg);
  }
}

/* -------- PSEUDO CLASS --------- */

/* -------- MEDIA QUERY --------- */

@media (max-width: 800px) {
  
}


</style>
