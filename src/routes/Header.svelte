<script>
	import { page } from '$app/stores';
	import logo from '$lib/images/svelte-logo.svg';
	import github from '$lib/images/github.svg';
	import { Navbar, NavBrand, NavLi, NavUl, NavHamburger, Button } from 'flowbite-svelte';
	import { DarkMode } from 'flowbite-svelte';
</script>

<header>
	<Navbar let:hidden let:toggle rounded color="form">
		<NavBrand href="/">
			<img src={logo} class="mr-3 h-6 sm:h-9" alt="Flowbite Logo" />
			<span class="self-center whitespace-nowrap text-xl font-semibold dark:text-white"
				>My Test App</span
			>
		</NavBrand>
		<NavHamburger on:click={toggle} />
		<NavUl {hidden}>
			<NavLi href="/" active={true}>Accueil</NavLi>
			<NavLi href="/about">A propos</NavLi>
			<NavLi href="/dashboard">Dashboard</NavLi>
			<NavLi href="/sverdle">Sverdle</NavLi>
			<NavLi href="/contact">Contact</NavLi>
		</NavUl>
		<DarkMode>Dark</DarkMode>
	</Navbar>
</header>

<style>
</style>
