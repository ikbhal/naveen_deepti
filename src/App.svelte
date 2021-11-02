<script>
	import Video from './Video.svelte';
	import Particles from "svelte-particles";


  let particlesConfig = {
    particles: {
      color: {
        value: "#000",
      },
      links: {
        enable: true,
        color: "#000",
      },
      move: {
        enable: true,
      },
    },
  };

  let onParticlesLoaded = (event) => {
    const particlesContainer = event.detail.particles;

    // you can use particlesContainer to call all the Container class
    // (from the core library) methods like play, pause, refresh, start, stop
  };

  let onParticlesInit = (main) => {
    // you can use main to customize the tsParticles instance adding presets or custom shapes
  };

</script>

<main>
	<Particles
		id="tsparticles"
		options="{particlesConfig}"
		on:particlesLoaded="{onParticlesLoaded}"
		on:particlesInit="{onParticlesInit}"
	/>
	
	<Video/>


</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>