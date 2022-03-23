<script lang="ts">
  import logo from "./assets/svelte.png";
  import Table from "./components/table/Table.svelte";
  import Counter from "./lib/Counter.svelte";
  import Hello from "./lib/Hello.svelte";
  import { Router, Link, Route } from "svelte-navigator";
import TicTacToe from "./components/TicTacToe.svelte";
import FontPreview from "./components/FontPreview.svelte";
import Svg from "./components/Svg.svelte";
import {createArray} from "./lib/utils";



let days = createArray(1,31)
let month = createArray(1,12)
let selectedDay;
let selectedMonth;



</script>

<main>
	<select bind:value={selectedDay}>
		{#each days as question}
			<option value={question}>
				{question}
			</option>
		{/each}
	</select>
	<select bind:value={selectedMonth}>
		{#each month as question}
			<option value={question}>
				{question}
			</option>
		{/each}
	</select>

  <button class="btn" on:click={()=>{console.log(selected)}}>CLick</button>
<!-- 
  <Router>
    <nav>
      <Link to="/">Home</Link>
      <Link to="about">About</Link>
      <Link to="blog">Blog</Link>
    </nav>
    <div>
      <Route path="/">
        <Counter />
      </Route>
      <Route path="table">
        <input type="text" bind:value={name}>
        <Table inputName={name} />
      </Route>
      <Route path="game">
        <TicTacToe/>
      </Route>
      <Route path="font">
        <FontPreview/>
      </Route>
      <Route path="svg">
        <Svg/>
      </Route>
    </div>
  </Router> -->
</main>

<style>
</style>
