<script>
    import {
        Button,
        Card,
        Navbar,
        NavBrand,
        NavHamburger,
        NavLi,
        NavUl,
    } from "flowbite-svelte";
</script>

<Navbar fluid={true}>
    <NavBrand>
        <span class="text-xl font-bold">Abdulrahman</span>
    </NavBrand>

    <NavHamburger></NavHamburger>

    <NavUl>
        <NavLi>Home</NavLi>
        <NavLi>About me</NavLi>
        <NavLi>Projects</NavLi>
        <NavLi>Contact me</NavLi>
    </NavUl>
</Navbar>



<div
    class="w-full grid sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 justify-center-safe"
>
    {#each Array(100) as arr}
        <Card class="w-full">Hola senior</Card>
    {/each}
</div>
