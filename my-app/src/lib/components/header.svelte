<script lang="ts">
  import { NavBrand, NavHamburger } from "flowbite-svelte";

  let { home, about, works, skills, contact } = $props();

  // Estado manual para el menú
  let isMenuOpen = $state(false);

  // Función para navegar y cerrar el menú
  const navigate = (callback: () => void) => {
    callback();
    isMenuOpen = false;
  };
</script>

<header class="sticky top-0 z-50 h-[87px] w-full bg-[#070707] border-b border-white/10 flex items-center justify-between px-6">
    
    <NavBrand>
        <h1 class="text-3xl md:text-4xl text-cyan-700 font-bold">
            Martín<span class="text-white">Marrero</span>
        </h1>
    </NavBrand>

    <div class="md:hidden">
        <NavHamburger 
            onclick={() => (isMenuOpen = !isMenuOpen)} 
            class="text-cyan-700" 
        />
    </div>

    <nav 
        class="
            {isMenuOpen ? 'flex' : 'hidden'} 
            md:flex flex-col md:flex-row 
            absolute md:static 
            top-[87px] left-0 w-full md:w-auto 
            bg-[#070707] md:bg-transparent 
            border-b md:border-none border-white/10
            z-40
        "
    >
        <ul class="flex flex-col md:flex-row gap-2 md:gap-8 p-6 md:p-0">
            <li>
                <button class="w-full text-left md:text-center cursor-pointer font-heading text-xl text-cyan-700 hover:text-white transition-colors" 
                   onclick={() => navigate(home)}>Home</button>
            </li>
            <li>
                <button class="w-full text-left md:text-center cursor-pointer font-heading text-xl text-cyan-700 hover:text-white transition-colors" 
                   onclick={() => navigate(about)}>About Me</button>
            </li>
            <li>
                <button class="w-full text-left md:text-center cursor-pointer font-heading text-xl text-cyan-700 hover:text-white transition-colors" 
                   onclick={() => navigate(works)}>Works</button>
            </li>
            <li>
                <button class="w-full text-left md:text-center cursor-pointer font-heading text-xl text-cyan-700 hover:text-white transition-colors" 
                   onclick={() => navigate(skills)}>Skills</button>
            </li>
            <li>
                <button class="w-full text-left md:text-center cursor-pointer font-heading text-xl text-cyan-700 hover:text-white transition-colors" 
                   onclick={() => navigate(contact)}>Contact</button>
            </li>
        </ul>
    </nav>
</header>