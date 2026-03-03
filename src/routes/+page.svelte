<script lang="ts">
  import Marquee from "svelte-fast-marquee";
  import choco from "$lib/assets/choco.png";
  import { onMount } from "svelte";
  import SunIcon from "$lib/SunIcon.svelte";
  import MoonIcon from "$lib/MoonIcon.svelte";

  const YSWS: { [type: string]: string } = {
    "Summer of Making": "https://summer.hackclub.com",
    Siege: "https://siege.hackclub.com",
    Carnival: "https://carnival.hackclub.com/",
    Flavortown: "https://flavortown.hackclub.com/",
  };

  const projects = [
    {
      name: "Cat Pictures",
      github: "https://github.com/Sivayogeith/cat-pictures",
      demo: "https://sivayogeith.github.io/cat-pictures",
      description:
        "A website with pictures of all the cats I have fed and met!",
      image: "/catPictures.png",
      ysws: "Summer of Making",
    },
    {
      name: "Minecraft Mod List",
      github: "https://github.com/Sivayogeith/mc-modlist",
      demo: "https://mc-modlist.vercel.app/",
      description:
        "This is a website where you enter all your minecraft mods and it tells you how many are compatible with a given version.",
      image: "/mcModList.png",
      ysws: "Siege",
    },
    {
      name: "Rice Minecraft Mod",
      github: "https://github.com/Sivayogeith/rice",
      demo: "https://modrinth.com/mod/rice-mod",
      description:
        "This minecraft mod adds rice and rice-related items to the game!",
      image: "/riceMod.png",
      ysws: "Summer of Making",
    },
    {
      name: "Sage's Portfolio",
      github: "https://github.com/Sivayogeith/portfolio",
      demo: "https://themeowingsage.vercel.app/",
      description: "This website!",
      image: "/portfolio.png",
      ysws: "Flavortown",
    },
    {
      name: "Math Clicker",
      github: "https://github.com/Sivayogeith/math-clicker",
      demo: "https://meth-clicker.vercel.app",
      description: "Math clicker game that is made with no engine.",
      image: "/mathClicker.png",
      ysws: "CodeQuest",
    },
    {
      name: "Icecream Flavours",
      github: "https://github.com/Sivayogeith/icecream-flavors",
      demo: "https://icecream-flavors.vercel.app/",
      description: "A website where I rank icecream flavors!",
      image: "/icecreamFlavours.png",
      ysws: "Summer of Making",
    },
    {
      name: "Peek Links",
      github: "https://github.com/Sivayogeith/peek-links",
      demo: "https://icecream-flavors.vercel.app/",
      description:
        "Extension that adds better and customizable link preview then the default one.",
      image: "/peekLinks.png",
      ysws: "Carnival",
    },
    {
      name: "Coin Clicker",
      github: "https://github.com/Sivayogeith/coin-clicker",
      demo: "https://github.com/Sivayogeith/coin-clicker/releases/tag/1.0.0",
      description:
        "Android clicker game where the roles of the coin and you are reversed.",
      image: "/coinClicker.jpg",
      ysws: "Siege",
    },
    {
      name: "Gobble Felix's Rats",
      github: "https://github.com/Sivayogeith/gobble-felixs-rats",
      demo: "https://modrinth.com/mod/gobble-felixs-rats",
      description:
        "This minecraft mod makes cats gobble (kill) nearby rats from Felix's Rats (another mod).",
      image: "/gobbleFelixsRats.png",
      ysws: "Siege",
    },
    {
      name: "Summer of Making Countdown",
      github: "https://github.com/Sivayogeith/som-countdown",
      demo: "https://som-countdown.vercel.app/",
      description:
        "This website counts down the inevitable end of Summer of Making!",
      image: "/somCountdown.png",
      ysws: "Summer of Making",
    },
    {
      name: "Gravity Stars",
      github: "https://github.com/Sivayogeith/gravity-stars",
      demo: "https://sivayogeith.github.io/gravity-stars/",
      description:
        "A game where you are a purple dude who has to collect all the stars without touching the ground to win!",
      image: "/gravityStars.png",
    },
  ];

  const socialMedia = [
    {
      name: "Github",
      link: "https://github.com/Sivayogeith",
      description: "This is where I upload all my coding projects!",
    },
    {
      name: "Youtube",
      link: "https://youtube.com/@themeowingsage/",
      description:
        "I upload minecraft videos, mainly PvP! <br> (I used to upload cats!) ",
    },
  ];

  let theme = $state("");

  onMount(() => {
    if (!localStorage.getItem("theme")) {
      theme = window.matchMedia("(prefers-color-scheme: dark)")
        ? "dark"
        : "light";
    } else {
      theme = localStorage.getItem("theme") || "light";
    }
  });

  $effect(() => {
    document.body.setAttribute("data-theme", theme);
    localStorage.setItem("theme", theme);
  });
</script>

<div class="flex 2xl:flex-row flex-col justify-between m-12 gap-10">
  <div
    class="flex lg:flex-row flex-col items-center 2xl:w-[70vw] lg:gap-0 gap-10"
  >
    <img src={choco} class="rounded-full me-12 size-60" alt="choco pic :3" />
    <div>
      <h1 class="text-5xl mb-4">
        Sivayogeith <span class="text-2xl">aka Sage, themeowingsage</span>
      </h1>
      <p class="text-xl">
        just a 14 y/o American Indian boy that loves to code, minecraft and
        food!
      </p>
    </div>
  </div>

  <div class="flex flex-col">
    <button
      onclick={() => (theme = theme == "dark" ? "light" : "dark")}
      class="dark:bg-[#f1ded9] bg-[#260902] dark:text-black text-white rounded-full p-2"
    >
      {#if theme == "dark"}
        <SunIcon />
      {:else}
        <MoonIcon />
      {/if}
    </button>
  </div>
</div>
<h1 class="text-center mt-8 mb-5 text-xl">projects :3</h1>

<div class="grid 2xl:grid-cols-3 xl:grid-cols-2 grid-col-1 gap-5 mx-10">
  {#each projects as p}
    <div
      class="rounded-xl border border-red-800 dark:border-red-500 p-5 hover:shadow-xl shadow-red-300 dark:shadow-red-700 shadow-(right)"
    >
      <div class="flex justify-between mb-5 md:flex-row flex-col">
        <div class="flex flex-col md:mb-0 mb-5">
          <p class="text-3xl">{p.name}</p>
          <div class="text-lg flex gap-4 text-red-800 dark:text-red-500">
            <a
              href={p.github}
              class="hover:text-red-700 dark:hover:text-red-400">Github</a
            >
            <a href={p.demo} class="hover:text-red-700 dark:hover:text-red-400"
              >Demo</a
            >
          </div>
          {#if Object.hasOwn(p, "ysws")}
            <p class="text-m">
              Submitted to
              {#if Object.hasOwn(YSWS, p.ysws)}
                <a
                  href={YSWS[p.ysws]}
                  target="_blank"
                  class="text-red-800 dark:text-red-500 hover:text-red-700 dark:hover:text-red-400"
                >
                  {p.ysws}
                </a>
              {:else}
                {p.ysws}
              {/if}
            </p>
          {/if}
        </div>
        <img
          src={p.image}
          alt={p.name}
          class="w-auto ms-2 md:max-w-50 max-w-60 max-h-30 rounded-2xl border border-red-800 dark:border-red-500 self-center"
        />
      </div>
      <p class="text-xl">
        {p.description}
      </p>
    </div>
  {/each}
</div>
<h1 class="text-center mt-8 mb-5 text-xl">favorite foods :3</h1>
<hr class="text-red-800 dark:border-red-500" />
<Marquee gap="10rem" class="text-2xl overflow-hidden my-5">
  <span>Idly</span>
  <span>Chocolate</span>
  <span>Pasta</span>
  <span>Pizza</span>
  <span>Ramen</span>
  <span>Payasam</span>
  <span>Burgers</span>
  <span>Cake</span>
</Marquee>
<hr class="text-red-800 dark:border-red-500" />
<h1 class="text-center mt-8 mb-5 text-xl">social media :3</h1>
<div class="grid 2xl:grid-cols-3 xl:grid-cols-2 grid-col-1 gap-5 mx-10">
  {#each socialMedia as s}
    <div
      class="rounded-xl border border-red-800 dark:border-red-500 p-5 flex flex-col gap-5 hover:shadow-xl shadow-red-300 dark:shadow-red-700"
    >
      <a
        href={s.link}
        target="_blank"
        class="text-3xl text-red-800 dark:text-red-500 hover:text-red-700"
        >{s.name}</a
      >
      <p class="text-xl">
        {@html s.description}
      </p>
    </div>
  {/each}
</div>

<footer
  class="flex justify-center text-xl px-10 py-5 bg-[#f2d4cb] dark:bg-red-950 mt-8"
>
  <p>by sage with {":3"}</p>
</footer>
