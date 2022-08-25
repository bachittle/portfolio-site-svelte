<script>
    export let shownPage;
</script>

<div class="projects">
    <h2>Projects</h2>
    <div class="cards">
        <a href="https://github.com/bachittle/uwindsor-timetable-scraper" class="card">
            <h3>UTable</h3>
        </a>
        <a href="https://github.com/bachittle/visual-sorting-online" class="card">
            <h3>visual-sorting-online</h3>
        </a>
        <a href="https://github.com/bachittle/playlist-creator" class="card">
            <h3>playlist creator</h3>
        </a>
    </div>
    <div class="back-btn">
        <button on:click={()=>{shownPage = "Intro";}}>Go back to home page</button>
    </div>
</div>

<style>
    /* projects shows list of projects I worked on. Javascript list has data. Data is rendered via an each block */
    .projects {
        background-color: #1e1f2e;
        padding: 2em 2em;
        margin: 0 0;
        
        font-family: 'Vollkorn', serif;
    }

    a {
        color: white;
        text-decoration: none;
        font-family: 'Rubik', sans-serif;
    }
    h2 {
        text-align: center;
    }
    .cards {
        display: flex;
        justify-content: space-around;
        flex-direction: column;
        text-align: center;
    }
    
    .card {
        background-color: #0A161F;
    }
    
    .back-btn {
        display: flex;
        justify-content: center;
        margin: 40px;
    }
    
    button {
        background-color: #0A161F;
        border: none;
        color: white;
        padding: 10px 20px;
        text-align: center;
        text-decoration: none;
        display: inline-block;
        font-size: 16px;
        
    }
    

  
</style>