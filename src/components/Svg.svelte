<script lang="ts">
  import Chart from "chart.js/auto";
import { afterUpdate } from "svelte";
  const labels = ["January", "February", "March", "April", "May", "June"];

  const data = {
    labels: labels,
    datasets: [
      {
        label: "My First dataset",
        backgroundColor: "rgb(255, 99, 132)",
        borderColor: "rgb(255, 99, 132)",
        data: [0, 10, 5, 2, 20, 30, 45],
      },
    ],
  };

  let chartCanvas;
  
  const config = {
    type: "line",
    data: data,
    options: {
       responsive: true,
       width:400,
       height:400
    },
  };
  

  afterUpdate(()=>{
    let ctx = chartCanvas.getContext('2d')
    const myChart = new Chart(chartCanvas, config);
  })
</script>

<!-- <svelte:head>
	<script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
</svelte:head> -->
<div>
  <h1>Hello svg</h1>
  <canvas bind:this={chartCanvas} width={400} height={400} >
    </canvas>
  





</div>

<style>
  canvas {
    width: 400px;
    height: 400px;
  }
</style>
