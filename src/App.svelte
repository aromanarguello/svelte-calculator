<script>
  import Navbar from "./Navbar.svelte";
  import Numpad from "./Numpad.svelte";

  const numbers = Array.from({ length: 10 }, (v, k) => k);
  numbers.push(".");
  let num = 0;
  let firstNum = 0;
  let secondNum = 0;
  const addNumberToState = val =>
    num === 0 ? (firstNum = val) : (secondNum = val);
  const add = val => (num = firstNum + secondNum);
  console.log(firstNum);
</script>

<Navbar title={'Calculator'} />
<main>
  <Numpad on:click={addNumberToState} {numbers} />
  <h2>{num}</h2>
  <section>
    <button on:click={e => add(e.target.value)}>+</button>
  </section>
</main>
