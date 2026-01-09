<script>
    let { color } = $props();
    import About from "$lib/components/about.svelte";
    import Works from "$lib/components/works.svelte";
    import Contact from "$lib/components/contact.svelte";
    import Skills from "$lib/components/skills.svelte";
    import Home from "$lib/components/home.svelte";

</script>

<div class="w-[90%] h-[80%] mx-auto my-15 p-4 border-2 relative flex-col flex gap-8">
    <header class=" border-2 border-b-cyan-700 flex-1">
        <h2 class="text-5xl p-2 text-center text-cyan-700 text-shadow-cyan-400 text-shadow-md">
            {#if color === 'red'}
                Welcome
            {:else if color === 'green'}
                About me
            {:else if color === 'yellow'}
                Works
            {:else if color === 'purple'}
                Contact
            {:else if color === 'orange'}
                Skills
            {/if}
        </h2>
    </header>
    <main id="bg" class=" w-full h-[90%] border-4 m-auto overflow-scroll">
        {#if color === 'red'}
            <Home>
            </Home>
        {:else if color === 'green'}
            <About>
            </About>
        {:else if color === 'yellow'}
            <Works>
            </Works>
        {:else if color === 'orange'}
            <Skills>
            </Skills>
        {:else if color === 'purple'}
            <Contact>
            </Contact>
        {/if}
    </main>
</div>
