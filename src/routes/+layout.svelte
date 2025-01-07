<script>
    import "../app.css";
    import { Navbar, NavBrand, NavLi, NavUl, NavHamburger } from 'flowbite-svelte'
    import { Dropdown, DropdownItem, DropdownDivider, DropdownHeader } from 'flowbite-svelte';
</script>

<Navbar let:hidden let:toggle>
    <NavBrand href="/">
      <img
        src="https://media.ducati.com/EPCResources/GRAPHICS/immagini_apparel/FC/FC8FA9B3580612309DD49F83D65719FD.png"
        class="mr-3 h-6 sm:h-9"
        alt="panigale v4 Logo"
      />
      <span class="self-center whitespace-nowrap text-xl font-semibold dark:text-white">&lt--Panigale</span>
    </NavBrand>
    <NavHamburger on:click={toggle} />
    <NavUl {hidden}>
      <NavLi href="/" active={true}>Home</NavLi>
      <NavLi href="/tabella">Table</NavLi>
      <NavLi href="/lista">List</NavLi>
    </NavUl>
  </Navbar>
<slot>

</slot>
