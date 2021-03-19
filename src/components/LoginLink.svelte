<script>
  import user from "../stores/user.js";
  import { link } from "svelte-routing";
  // logout func
  import globalStore from "../stores/globalStore.js";
</script>

{#if $user.jwt}
  <a
    href="/"
    class="logout-btn"
    on:click={() => {
      globalStore.toggleItem("sidebar", false);
    }}>logout</a
  >
{:else}
  <a
    href="/login"
    on:click={() => {
      globalStore.toggleItem("sidebar", false);
    }}>login</a
  >
{/if}
