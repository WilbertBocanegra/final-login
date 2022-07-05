<script>
  import { onMount } from "svelte";

  /**
   * @type {HTMLIFrameElement}
   */
  let component;

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
    component.contentWindow.postMessage(
      "hola",
      "https://pet-final.vercel.app/"
    );
    document.cookie = `${value}=${value2}; SameSite=None; Secure`;
  };
</script>

<h1>HOLA</h1>
<h1>LOGIN</h1>

<input bind:value placeholder="key" />
<input bind:value={value2} placeholder="name" />

<button on:click={setCookie}>set</button>

<iframe
  bind:this={component}
  src="https://pet-final.vercel.app/"
  title={undefined}
/>
