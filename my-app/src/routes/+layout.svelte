<script lang="ts">
	import { injectSpeedInsights } from '@vercel/speed-insights/sveltekit';
	import './layout.css';
	
	let { children } = $props();
	injectSpeedInsights();
</script>

{@render children()}

