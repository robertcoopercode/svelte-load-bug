<script context="module">
  import { todosStore } from "$lib/store";

  export const load = async () => {
    console.log("Loading about");

    const waitTwoSeconds = async () => {
      return new Promise((resolve) => {
        setTimeout(() => {
          resolve();
        }, 2000);
      });
    };

    todosStore.set(["four", "five", "six"]);

    await waitTwoSeconds();

    return {
      props: {},
    };
  };
</script>

<svelte:head>
  <title>About</title>
</svelte:head>

<section>
  <h1>About</h1>

  {#each $todosStore as todo}
    <p>{todo}</p>
  {/each}
</section>

<style>
  section {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    flex: 1;
  }

  h1 {
    width: 100%;
  }
</style>
