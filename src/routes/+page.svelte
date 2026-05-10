<script>
    import {
        Navbar,
        NavBrand,
        NavHamburger,
        NavLi,
        NavUl,
        P,
    } from "flowbite-svelte";
    import Card from "./Card.svelte";
    import { onMount } from "svelte";

    let projects = $state([]);

    onMount(async () => {
        let data = await fetch("/projects.json");
        projects = (await data.json());
        console.log(projects[0]);
        
    });


</script>

<Navbar fluid={true}>
    <NavBrand>
        <span class="text-xl font-bold">Abdulrahman</span>
    </NavBrand>

    <NavHamburger></NavHamburger>

    <NavUl>
        <NavLi>Home</NavLi>
        <NavLi href="#about-me">About me</NavLi>
        <NavLi href="#projects">Projects</NavLi>
        <NavLi>Contact me</NavLi>
    </NavUl>
</Navbar>

<div class="p-4" id="about-me">
    <div class="w-full text-lg font-semibold">
        About me

        <P class="font-light text-md" >
            I’m a computer engineer focused on QA automation, backend
            development, and development tooling. My primary focus is building
            reliable testing workflows using Playwright, Docker, GitHub Actions,
            and modern JavaScript/TypeScript ecosystems. I enjoy creating
            maintainable test infrastructure, automating workflows, and
            improving software reliability through practical engineering
            solutions. Beyond QA, I also work with Node.js backend development,
            Flutter applications, and game development using Godot and Blender.
        </P>
    </div>

    <div class=" w-full text-lg font-semibold" id="projects">Projects</div>

    <div
        class="w-full grid gap-4 sm:grid-cols-1 md:grid-cols-2 lg:grid-cols-3 justify-center-safe"
    >
        {#each projects as project}
            <Card title={project.projectName} description={project.projectDesc} briefDescription={project.projectBriefDesc} link={project.projectLink} imageLink={project.image}></Card>
        {/each}
    </div>
</div>
