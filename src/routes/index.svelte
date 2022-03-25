<script context="module">
  import { todosStore } from "$lib/store";

  export const load = () => {
    console.log("Loading home");
    todosStore.set(["one", "two", "three"]);

    return {
      props: {},
    };
  };
</script>

<svelte:head>
  <title>Home</title>
</svelte:head>

<section>
  <h1>Home</h1>

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
