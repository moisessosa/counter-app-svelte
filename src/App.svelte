<script lang="ts">
  let counter: number = 0;
  //const add = (): number => counter++;
  //const subtract = (): number => counter--; otro jeito
  const modifyCounter = (value: number): number => (counter += value);

  function reset(): void {
    counter = 0;
  }
</script>

<main>
  <h1 on:click={reset}>Counter App<!--{name} {lastName}!--></h1>
  <hr />
  <h2 class={counter >= 0 ? "add" : "subtract"}>Counter: {counter}</h2>
  <!--<button class="add" on:click={add}>+1</button> asi era antes
    pero el evento click pasa como argumento algo del tipo mouse handelr y por eso tenemos 
    que pasar el argumento como una funcion anonima-->
  <button class="add" on:click={() => modifyCounter(1)}>+1</button>
  <button class="subtract" on:click={() => modifyCounter(-1)}>-1</button>
  <button class="reset" on:click={reset}>Reset</button>
</main>

<style>
  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
  }

  h1 {
    color: #ff3e00;
    text-transform: uppercase;
    font-size: 4em;
    font-weight: 100;
  }
  h2 {
    font-size: 2rem;
  }
  button {
    font-size: 2rem;
    margin: 0 0.4rem;
    border-radius: 5px;
  }
  button.reset {
    color: aliceblue;
    background: #ff3e00;
  }
  button:hover {
    cursor: pointer;
  }
  .add {
    background-color: #26d231;
  }
  .add:hover {
    background-color: #16b623;
  }
  .subtract {
    background-color: #3a9aea;
  }
  .subtract:active {
    background-color: rgb(20, 55, 83);
  }
  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>
