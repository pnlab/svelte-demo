<script>
  let current = "X";
  let board = [
    ["", "", ""],
    ["", "", ""],
    ["", "", ""],
  ];
  const winCheck=() =>{

  }

  const handleClick = (i, j) => {
    board[i][j] = current;
    current = current === "X" ? "O" : "X";
  };
</script>

<h1>Game</h1>

<h1>Player: {current}</h1>

<table>
  {#each board as row, i}
    <tr>
      {#each row as cell, j}
        <td  on:click={()=>handleClick(i, j)}>{cell}</td>
      {/each}
    </tr>
  {/each}
</table>

<style>
  tr,
  td {
    width: 10rem;
    height: 10rem;
    border: 1px solid black;
    padding: 10px;
    text-align: center;
    font-size: 5rem;
  }
  table {
    border-spacing: 3rem 3rem;
  }
  td {
    cursor: pointer;
  }
</style>
