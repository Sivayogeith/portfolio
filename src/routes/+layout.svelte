<script lang="ts">
  import "../app.css";
  import choco from "$lib/assets/choco.png";

  let { children } = $props();
</script>

<svelte:head>
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link
    rel="preconnect"
    href="https://fonts.gstatic.com"
    crossorigin="anonymous"
  />
  <link
    href="https://fonts.googleapis.com/css2?family=Saira:ital,wght@0,100..900;1,100..900&display=swap"
    rel="stylesheet"
  />

  <link rel="icon" href={choco} />
  <title>Sage's Portfolio</title>

  <style>
    body {
      font-family: "Saira", sans-serif;
    }
  </style>
</svelte:head>

{@render children()}
