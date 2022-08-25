<script>
    // this script will draw to the canvas element.
    // it will spawn a bunch of particles that perform certain tasks. 
    // the default use case is orbit. More may be implemented in the future. 
    import { onMount } from 'svelte';
    
    let canvas;
    
    onMount(() => {
        const orbit = {
            radius: 0,
            xOffset: 0,
            yOffset: -60
        };
        const resizeHandler = () => {
            canvas.width = canvas.offsetWidth;
            canvas.height = canvas.offsetHeight;
            orbit.radius = canvas.height / 4;
        }
        
        
        addEventListener('resize', resizeHandler);
        resizeHandler();

        const ctx = canvas.getContext("2d");
        let counter = 0;
        
        const particles = [];
        let uid = 0;
        class Particle {
            constructor(radius, orbitOffset) {
                this.radius = radius;
                this.orbitOffset = orbitOffset;

                this.id = uid;
                uid++;
                
                this.speed = 0.01;
            }

            // called each frame, update should make changes to the properties of Particle, but not draw anything.
            update() {
                this.x = canvas.width/2 + orbit.xOffset + Math.sin(this.id + counter*this.speed) * -(orbit.radius + this.orbitOffset);
                this.y = canvas.height/2 + orbit.yOffset + Math.cos(this.id + counter*this.speed) * (orbit.radius + this.orbitOffset);
            }

            // called each frame, renders to the screen. 
            draw() {
                ctx.beginPath();
                ctx.arc(this.x, this.y, this.radius, 0, 2*Math.PI);
                ctx.fill();
            }
        }
        
        for (let i = 0; i < 50; i++) {
            particles.push(new Particle(
                Math.random() * 5 + 2,
                Math.random()*20
            ));
        }

        // animation loop
        function animate() {
            requestAnimationFrame(animate);
            ctx.clearRect(0,0,canvas.width,canvas.height);
            
            ctx.fillStyle = "rgba(255, 224, 51, 0.4)";
            
            particles.forEach(particle => {
                particle.update();
                particle.draw();
            });
            
            counter++;
        }
        animate();
    });

</script>

<canvas bind:this={canvas}></canvas>

<style>
    canvas {
        position: absolute;
        top: 0;
        left: 0;
        /* border: 5px solid black; */
        width: 100vw;
        height: 100vh;
        z-index: -1;
    }
</style>