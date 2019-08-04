<script>
  export let numbers;
  export let handleNum;
</script>

<style>
  .wrapper {
    border: 1px solid red;
    height: auto;
    width: 500px;
    height: 300px;
    margin: 0 auto;
    display: inline-block;
  }

  .numberpad-container {
    width: 150px;
    margin: 0;
    height: auto;
    display: flex;
    flex-wrap: wrap;
    justify-content: space-around;
  }

  button {
    margin: 5px;
    height: 30px;
    width: 30px;
    padding: 0;
    border-radius: 2px;
    background-color: #3071e4;
    color: white;
    font-weight: 500;
  }

  button:last-child {
    width: 82px;
  }
</style>

<section class="wrapper">
  <aside class="numberpad-container">
    {#each numbers.sort((a, b) => a - b) as number}
      <button on:click={e => handleNum(e.target.value)}>{number}</button>
    {/each}
  </aside>
</section>
