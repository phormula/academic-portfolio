<script lang="ts">
  import { Nav, NavItem, NavLink } from 'sveltestrap';
  import { onMount } from 'svelte';

  let hash = window.location.hash;

  onMount(() => {
    if (hash) {
      const section = document.getElementById(hash.slice(1));
      if (section) {
        section.scrollIntoView({ behavior: 'smooth' });
      }
    }
  });

  $: if (hash) {
    const section = document.getElementById(hash.slice(1));
    if (section) {
      section.scrollIntoView({ behavior: 'smooth' });
    }
  }
  const hashChangeHandler = () => {
    hash = window.location.hash;
  };
</script>

<svelte:window on:hashchange={hashChangeHandler} />

<div class="mx-auto">
  <Nav justified navbar>
    <NavItem>
      <NavLink href="/">About</NavLink>
    </NavItem>
    <NavItem>
      <NavLink href="#publication">Publications</NavLink>
    </NavItem>
    <NavItem>
      <NavLink href="#research">Research</NavLink>
    </NavItem>
    <NavItem>
      <NavLink href="#software">Software</NavLink>
    </NavItem>
    <NavItem>
      <NavLink href="#contact">Contact</NavLink>
    </NavItem>
  </Nav>
</div>
