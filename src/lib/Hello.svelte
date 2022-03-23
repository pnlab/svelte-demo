<script lang="ts">
  let btn: HTMLElement = null;
  let n: number;
  const handleClick = () => {
    
    console.log(btn.className);
  };
</script>

<h1 class="h1" bind:this={btn}>Hello</h1>

<button  on:click={handleClick}>Click me</button>

<style>
  .h1 {
    color: rgba(167, 158, 79, 0.904);
  }
</style>
