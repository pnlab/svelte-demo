<script lang='ts'>

let a:HTMLElement ;
	let questions = [
		{ id: 1, text: `Where did you go to school?` },
		{ id: 2, text: `What is your mother's name?` },
		{ id: 3, text: `What is another personal fact that an attacker could easily find with Google?` }
	];

	let selected;
const handleClick = ()=>{
  a.style.fontFamily="monospace"
}

</script>
<select value={selected}>
		{#each questions as question}
			<option value={question}>
				{question.text}
			</option>
		{/each}
	</select>
<button on:click={handleClick}>Change</button>

<div bind:this={a} class="font">Font</div>

<style>
.font {
  font-size: 20rem;
}
@keyframes example {
  from {background-color: red;}
  to {background-color: yellow;}
}
div {
  width: 100px;
  height: 100px;
  background-color: red;
  animation-name: example;
  animation-duration: 4s;
}
</style>