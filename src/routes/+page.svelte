<script>


    import {Navbar, NavBrand, NavHamburger, NavLi, NavUl} from "flowbite-svelte"
</script>



<Navbar fluid={true}>

    <NavBrand>
        <span class="text-xl font-bold">Abdulrahman</span>
    </NavBrand>

    <NavHamburger></NavHamburger>

    <NavUl>

        <NavLi> Home</NavLi>
        <NavLi> About me</NavLi>
        <NavLi> Projects</NavLi>
        <NavLi> Contact me</NavLi>
    </NavUl>
</Navbar>


