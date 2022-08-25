<script>
    import ParticleAnim from "./ParticleAnim.svelte";
    import Typewriter from "./Typewriter.svelte";

    import DiGithubBadge from 'svelte-icons/di/DiGithubBadge.svelte'
    import FaFileAlt from 'svelte-icons/fa/FaFileAlt.svelte'
    import FaLinkedin from "svelte-icons/fa/FaLinkedin.svelte";
    import FaProjectDiagram from "svelte-icons/fa/FaProjectDiagram.svelte";
    
    export let shownPage;
</script>

<div class="intro">
    <ParticleAnim />
    <div class="my-text">
      <h1 class="title"><Typewriter text={'Bailey Chittle'} eraseText={false}/></h1>
      <p class="description"><Typewriter texts={[
        "Software engineer",
        "Currently employed to write efficient C++ for ultrasonic systems",
        `"The more you know, the more you realize you know nothing" -Socrates`,
        "I have experience in web development and project management",
        "while(isAlive) {eat();code();sleep();}",
        "My CSS is !important",
        `$("#Github").click();`,
      ]}/></p>
    </div>

    <div class="logo-icons">
      <a class="icon gh-icon" href="https://github.com/bachittle" target="_blank">
        <DiGithubBadge />
        <p>Github</p>
      </a>
      <a class="icon in-icon" href="https://linkedin.com/in/bailey-chittle" target="_blank">
        <FaLinkedin />
        <p>Linkedin</p>
      </a>
      <a class="icon resume-icon" href="/cv.pdf" target="_blank">
        <FaFileAlt />
        <p>resume</p>
      </a>
      <a class="icon resume-icon" href="#" on:click={() => {shownPage = "Projects";}}>
        <FaProjectDiagram />
        <p>projects</p>
      </a>
    </div>
</div>

<style>
  /* intro displays name, description, and logos */
  .intro {
    height: 100%;
    text-align: center;
    display: flex;
    flex-direction: column;
    justify-content: flex-end;
    gap: calc(33vh - 50px);
    padding: 100px 0px;
  }
  .title {
    height: 39px;
  }
  .description {
    height: 19px;
    margin: 3em 4em;
  }

  .logo-icons {
    margin: 0 10% 0 5%;
    display: flex;
    justify-content: space-around;
  }
  .icon {
    height: 70px;
    margin: 0 1em;
    color: white;
  }
  /* .gh-icon {
    position: relative;
    bottom: 5px;
    left: 15px;
    height: 95px;
  } */
  
</style>