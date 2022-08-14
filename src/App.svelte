<script>
  import Typewriter from "./lib/Typewriter.svelte";
  import DiGithubBadge from 'svelte-icons/di/DiGithubBadge.svelte'
  import FaFileAlt from 'svelte-icons/fa/FaFileAlt.svelte'
  import FaProjectDiagram from "svelte-icons/fa/FaProjectDiagram.svelte";
import FaLinkedin from "svelte-icons/fa/FaLinkedin.svelte";
  
  const logos = {
    
  };
</script>

<div class="my-text">
  <h1><Typewriter text={'Bailey Chittle'} eraseText={false}/></h1>
  <p><Typewriter texts={[
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
  <div class="icon">
    <DiGithubBadge />
  </div>
  <div class="icon">
    <FaFileAlt />
  </div>
  <div class="icon">
    <FaProjectDiagram />
  </div>
  <div class="icon">
    <FaLinkedin />
  </div>
</div>

<style>
  .my-text {
    text-align: center;
    margin: 10% 0 2% 0;
  }
  .logo-icons {
    display: flex;
    justify-content: space-around;
  }
  .icon {
    width: 100px;
    margin: 0;
  }
</style>
