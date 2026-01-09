<script lang="ts">
  import Header from "../lib/components/header.svelte";
  import { fade } from 'svelte/transition';
  import Container from "$lib/components/container-cards.svelte";
  let option = $state('red');

  const setOption = (color: string) => {
    console.log("Opción cambiada a:", color);
    option = color;
  }

  import { onMount } from 'svelte';

	let canvas;

	onMount(() => {
		const ctx = canvas.getContext('2d');
		let w, h, stars = [];

		const init = () => {
			w = canvas.width = window.innerWidth;
			h = canvas.height = window.innerHeight;
			stars = Array.from({ length: 200 }, () => ({
				x: Math.random() * w,
				y: Math.random() * h,
				size: Math.random() * 2,
				speed: Math.random() * 0.5 + 0.1
			}));
		};

		const draw = () => {
			ctx.clearRect(0, 0, w, h);
			ctx.fillStyle = 'white';
			stars.forEach(s => {
				ctx.beginPath();
				ctx.arc(s.x, s.y, s.size, 0, Math.PI * 2);
				ctx.fill();
				s.y += s.speed;
				if (s.y > h) s.y = 0;
			});
			requestAnimationFrame(draw);
		};

		init();
		draw();
		window.addEventListener('resize', init);
		return () => window.removeEventListener('resize', init);
	});

</script>

<div class="fixed inset-0 bg-black -z-10">
	<canvas bind:this={canvas}></canvas>
</div>

<style>
	canvas {
		display: block;
	}
</style>
<Header
  home={() => setOption('red')}
  about={() => setOption('green')}
  works={() => setOption('yellow')}
  skills={() => setOption('orange')}
  contact={() => setOption('purple')}
  >
</Header>
<main>
	{#key option}
        <div in:fade={{ duration: 300 }} class="w-full">
            <Container color={option} />
        </div>
	{/key}
</main>
