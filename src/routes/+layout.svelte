<script lang="ts">
  import "../app.css";
  import favicon from "$lib/assets/favicon.svg";

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

  <link rel="icon" href={favicon} />

  <style>
    body {
      background: #f1ded9;
      min-height: 100vh;
      font-family: "Saira", sans-serif;
    }
  </style>
</svelte:head>

{@render children()}
