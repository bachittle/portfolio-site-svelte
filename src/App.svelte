<script>
import { fly, slide} from "svelte/transition";
import { quintOut } from 'svelte/easing';
import Intro from "./lib/Intro.svelte";
import Projects from "./lib/Projects.svelte";
  
let shownPage = "Intro";
</script>

{#if shownPage === "Intro"}
<div class="pages" transition:slide="{{delay: 50, duration: 500, easing: quintOut }}">
  <div class="page">
    <Intro bind:shownPage/>
  </div>
</div>
{/if}

{#if shownPage === "Projects"}
<div class="pages" transition:slide="{{delay: 50, duration: 500, easing: quintOut }}">
  <div class="page">
    <Projects bind:shownPage/>
  </div>
</div>
{/if}

<style>
  /* pages resemble 2 cards. Side by side horizontally when wide, otherwise side by side vertically. */
  .pages {
    display: flex;
    justify-content: center;
  }
  .page {
    width: 50%;
    height: 100vh;
    display: flex;
    justify-content: center;
    flex-direction: column;
  }
  
  @media (max-width: 820px) {
    .pages {
      display: flex;
      flex-direction: column;
    }
    .page {
      width: 100%;
      height: 100vh;
      display: flex;
      justify-content: center;
      flex-direction: column;
    }
  }
  
</style>
