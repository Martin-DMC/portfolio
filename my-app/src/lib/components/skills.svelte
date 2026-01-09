<script lang="ts">
  const skills = [
    { name: "Python", icon: "python", color: "#3776AB" },
    { name: "C", icon: "c", color: "#A8B9CC" },
    { name: "HTML5", icon: "html5", color: "#E34F26" },
    { name: "CSS3", icon: "css", color: "#1572B6" },
    { name: "JavaScript", icon: "javascript", color: "#F7DF1E" },
    { name: "Svelte", icon: "svelte", color: "#FF3E00" },
    { name: "Flask", icon: "flask", color: "#a8b9cc" },
    { name: "Tailwind", icon: "tailwindcss", color: "#06B6D4" },
    { name: "Flowbite", icon: "flowbite", color: "#3F83F8" },
    { name: "MySQL", icon: "mysql", color: "#4479A1" },
    { name: "MongoDB", icon: "mongodb", color: "#47A248" },
    { name: "Cypress", icon: "cypress", color: "#b5b8a0" },
    { name: "Pytest", icon: "pytest", color: "#0A9EDC" },
    { name: "Postman", icon: "postman", color: "#FF6C37" },
    { name: "GitHub Actions", icon: "githubactions", color: "#2088FF" },
  ];
</script>

<section class="max-w-5xl mx-auto py-12 px-6 rounded-2xl bg-[#000b]">
  <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-4">
    {#each skills as skill}
      <div 
        class="flex items-center gap-4 p-4 rounded-2xl border transition-all duration-300 group shadow-sm hover:shadow-md"
        style="
          background-color: {skill.color}10; 
          border-color: {skill.color}30;
        "
      >
        <div 
          class="w-10 h-10 flex items-center justify-center bg-white rounded-xl shadow-sm group-hover:scale-110 transition-transform duration-300"
        >
          <img 
            src="https://cdn.simpleicons.org/{skill.icon}/{skill.color.replace('#', '')}" 
            alt={skill.name} 
            class="w-6 h-6 object-contain"
            on:error={(e) => (e.currentTarget.src = "https://flowbite.com/docs/images/logo.svg")}
          />
        </div>
        
        <div class="flex flex-col">
          <span class="font-bold text-amber-50 text-sm md:text-base">
            {skill.name}
          </span>
          <span class="text-[10px] uppercase tracking-wider font-semibold opacity-60" style="color: {skill.color}">
            Tecnología
          </span>
        </div>
      </div>
    {/each}
  </div>
</section>