<script>
    import {
    A,
        Navbar,
        NavBrand,
        NavHamburger,
        NavLi,
        NavUl,
        P,
        Timeline,
        TimelineItem,
    } from "flowbite-svelte";
    import Card from "./Card.svelte";
    import { onMount } from "svelte";

    let projects = $state([]);

    onMount(async () => {
        let data = await fetch("/portfolio/projects.json");
        projects = (await data.json());
        console.log(projects[0]);
        
    });


</script>

<Navbar fluid={true}>
    <NavBrand>
        <span id="home" class="text-xl font-bold">Abdulrahman</span>
    </NavBrand>

    <NavHamburger></NavHamburger>

    <NavUl>
        <NavLi href="#home">Home</NavLi>
        <NavLi href="#about-me">About me</NavLi>
        <NavLi href="#projects">Projects</NavLi>
        <NavLi href="#contact-me">Contact me</NavLi>
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



        <div class="w-full text-lg font-semibold" id="contact-me">
        Contact me

        <P class="font-light text-md" >
        My email : abdulrahman.7.2k@gmail.com
        github : <A href="https://github.com/abody2k"> over here!</A>
        Phone number : +9647744415507
        WhatsApp : <A href="https://wa.link/343zey"> Click!</A>

        </P>
    </div>







        <div class="w-full text-lg font-semibold">
        Ongoing projects

<Timeline order="horizontal">
  <TimelineItem title="Pack Mann" date="Started on May 7 2026">
    {#snippet orientationSlot()}
      <span class="bg-primary-200 dark:bg-primary-900 absolute -left-4 flex h-6 w-6 items-center justify-center rounded-full ring-8 ring-white dark:ring-gray-900">
      </span>
    {/snippet}
    <p class="mb-4 pl-4 text-base font-normal text-gray-500 dark:text-gray-400">
      Started with an empty project
    </p>
  </TimelineItem>
  <TimelineItem title="Pack Mann early build" date="To be released on May 20 2026">
    {#snippet orientationSlot()}
      <span class="bg-primary-200 dark:bg-primary-900 absolute -left-4 flex h-6 w-6 items-center justify-center rounded-full ring-8 ring-white dark:ring-gray-900">
      </span>
    {/snippet}
    <p class="pl-4 text-base font-normal text-gray-500 dark:text-gray-400">
        Includes controller, playing and multiplayer logic. on top of using docker and github actions to auto deploy
    </p>
  </TimelineItem>

</Timeline>
    </div>
</div>
