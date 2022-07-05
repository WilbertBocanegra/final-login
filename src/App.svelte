<script>
  import { onMount } from "svelte";

  /**
   * @type {string}
   */
  let value;

  /**
   * @type {string}
   */
  let value2;

  onMount(() => {
    window.addEventListener("message", (e) => {
      console.log(e);
    });
  });

  const setCookie = () => {
    document.cookie = `${value}=${value2}; SameSite=None; Secure`;
  };
</script>

<h1>HOLA</h1>
<h1>LOGIN</h1>

<input bind:value placeholder="key" />
<input bind:value={value2} placeholder="name" />

<button on:click={setCookie}>set</button>
