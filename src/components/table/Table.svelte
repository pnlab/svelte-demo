<script lang="ts">
  import { each } from "svelte/internal";

  export let inputName: string;
  let inputAge: number;

  interface IUser {
    name: string;
    age: number;
  }

  let data: IUser[] = [
    {
      name: "Nguyen",
      age: 20,
    },
    {
      name: "Nguyen",
      age: 20,
    },
  ];
  const handleSumit = (e) => {
    e.preventDefault();
    const u = {
      name: inputName,
      age: inputAge,
    };
    data.push(u);
    data=data
    console.log(data)
    // inputName = "";
    // inputAge = null;
  };
</script>

<table>
  <thead>
    <tr>
      <th>Ten</th>
      <th>Tuoi</th>
    </tr>
  </thead>
  <tbody>
    {#each data as user}
      <tr>
        <td>{user.name}</td>
        <td>{user.age}</td>
      </tr>
    {/each}
  </tbody>
</table>
<div>
  <h1>Hello {inputName}</h1>
  <form on:submit={handleSumit}>
    <input bind:value={inputName} type="text" placeholder="enter name" />
    <input bind:value={inputAge} type="number" placeholder="enter age" />
    <button type="submit">ADD</button>
  </form>
</div>

<style>
  table,
  tr,
  th,
  td {
    border: 1px solid black;
    border-collapse: collapse;
    padding: 10px;
    text-align: center;
  }
</style>
