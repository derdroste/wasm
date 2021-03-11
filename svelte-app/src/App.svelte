<script>
  export let fibonacci;
  const amount = 40;

  function fibojs(num) {
    if (num <= 1) return 1;

    return fibojs(num - 1) + fibojs(num - 2);
  }
  const wasm = async () => {
    let now = Date.now();
    await fibonacci.fibonacci(amount);
    console.log(now - Date.now());
  };

  const js = async () => {
    let now = Date.now();
    await fibojs(amount);
    console.log(now - Date.now());
  };
</script>

<main>
  <button on:click={wasm}>wasm</button>
  <button on:click={js}>js</button>
  <p>
    Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn
    how to build Svelte apps.
  </p>
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

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>
