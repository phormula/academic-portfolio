<script lang="ts">
  import { Navbar, NavbarBrand, NavbarToggler, Collapse, Offcanvas } from 'sveltestrap';
  import MainMenu from './MainMenu.svelte';

  export let name: string;
  let isOpen = false;
  const toggle = () => (isOpen = !isOpen);

  function handleUpdate(event: any) {
    isOpen = event.detail.isOpen;
  }

  function generateLogo(name: string) {
    const nameArr = name.split(' ');
    const firtName = nameArr[0][0];
    const lastName = nameArr.pop()?.[0];

    return `${firtName}${lastName}`;
  }
</script>

<Navbar color="light" light expand="md" container>
  <NavbarBrand href="/">
    <div class="d-flex align-items-center justify-content-center p-2 me-3 user-initials">
      <span> {generateLogo(name)}</span>
    </div>
  </NavbarBrand>
  <Collapse navbar expand="md" on:update={handleUpdate}><MainMenu /></Collapse>
  <Offcanvas {isOpen} {toggle}>
    <h1 slot="header">Main Menu</h1>
    <MainMenu />
  </Offcanvas>
  <NavbarToggler on:click={() => (isOpen = !isOpen)} />
</Navbar>

<style>
  .user-initials {
    background-color: #7269ef;
    color: #fff;
    font-weight: 700;
    height: 50px;
    width: 50px;
    border-radius: 50%;
  }
</style>
