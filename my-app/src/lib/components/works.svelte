<script lang="ts">
    import Spotly from '$lib/statics/spotly-logo-color.png';
    import Hbnb from '$lib/statics/logo.png'
    import SpotlyDemo from '$lib/statics/flow-demo.cy.ts.mp4'
    const proyectos = [
        {
            titulo: "Spotly - Agente de Talento (Proyecto Final)",
            desc: "Plataforma para centralizar y filtrar datos masivos de candidatos. Trabajé como QA liderando el testing con Pytest, Cypress y GitHub Actions.",
            tags: ["QA Automation", "Cypress", "Python", "Data Filtering"],
            imagen: Spotly,
            repo: "https://github.com/team-gamma-devs",
            demo: SpotlyDemo,
            status: "QA Lead Role"
        },
        {
            titulo: "HBNB - AirBnB Clone",
            desc: "Réplica de la arquitectura de Airbnb. Gestión de base de datos MySQL con SQLAlchemy, backend en Flask y frontend HTML, CSS, JavaScript.",
            tags: ["Python", "Flask", "MySQL", "SQLAlchemy"],
            imagen: Hbnb,
            repo: "https://github.com/Martin-DMC/Freetime/tree/main/aplicacion_hbnb",
            demo: null,
            status: "Fullstack role"
        }
    ];
</script>

<div class="max-w-6xl mx-auto py-8 px-4">
    <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
        {#each proyectos as p}
            <div class="group relative bg-black/40 backdrop-blur-md rounded-3xl overflow-hidden border border-white/10 hover:border-cyan-500/50 transition-all duration-500 flex flex-col shadow-2xl">
                
                <div class="absolute inset-0 bg-gradient-to-b from-cyan-500/5 to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-500"></div>

                <div class="relative h-56 overflow-hidden">
                    <img src={p.imagen} alt={p.titulo} 
                        class="w-full h-full object-contain p-12 transition-transform duration-700 group-hover:scale-110 grayscale-[50%] group-hover:grayscale-0" />
                    
                    <div class="absolute top-4 right-4">
                        <span class="bg-cyan-900/80 text-cyan-300 text-[10px] px-3 py-1 rounded-full uppercase font-black tracking-widest border border-cyan-500/30 backdrop-blur-md">
                            {p.status}
                        </span>
                    </div>
                </div>

                <div class="p-8 flex flex-col flex-grow relative z-10">
                    <h3 class="text-2xl font-bold text-white mb-3 group-hover:text-cyan-400 transition-colors">
                        {p.titulo}
                    </h3>
                    
                    <p class="text-gray-400 text-sm leading-relaxed mb-6 flex-grow">
                        {p.desc}
                    </p>
                    
                    <div class="flex flex-wrap gap-2 mb-8">
                        {#each p.tags as tag}
                            <span class="px-3 py-1 bg-white/5 text-gray-300 text-[10px] rounded-lg border border-white/10 font-medium">
                                {tag}
                            </span>
                        {/each}
                    </div>

                    <div class="flex gap-4">
                        <a href={p.repo} target="_blank" 
                           class="flex-1 text-center py-3 border border-white/20 rounded-xl text-xs font-bold text-white hover:bg-white hover:text-black transition-all duration-300 uppercase tracking-widest">
                            Source Code
                        </a>
                        
                        {#if p.demo}
                            <a href={p.demo} target="_blank" 
                               class="flex-1 text-center py-3 bg-cyan-600 text-white rounded-xl text-xs font-bold hover:bg-cyan-500 shadow-lg shadow-cyan-900/20 transition-all duration-300 uppercase tracking-widest">
                                Live Demo
                            </a>
                        {:else}
                            <div class="flex-1 text-center py-3 bg-white/5 text-gray-500 rounded-xl text-[10px] font-bold uppercase tracking-widest border border-white/5 italic">
                                Private/Local
                            </div>
                        {/if}
                    </div>
                </div>
            </div>
        {/each}
    </div>
</div>