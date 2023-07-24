<script>
	import { page } from '$app/stores';
	import logo from '$lib/images/svelte-logo.svg';
	import github from '$lib/images/github.svg';
	import {
		Navbar,
		NavBrand,
		NavLi,
		NavUl,
		NavHamburger,
		Button,
		Drawer,
		CloseButton
	} from 'flowbite-svelte';
	import { DarkMode } from 'flowbite-svelte';
	import SideBar from './SideBar.svelte';
	import { sineIn } from 'svelte/easing';
	let hidden2 = true;
	let transitionParams = {
		x: -320,
		duration: 200,
		easing: sineIn
	};
	let session = true;
</script>

<header>
	<Navbar let:hidden let:toggle>
		<NavBrand href="/">
			<img src={logo} class="mr-3 h-6 sm:h-9" alt="Flowbite Logo" />
			<span class="self-center whitespace-nowrap text-xl font-semibold dark:text-white">
				My Super App
			</span>
		</NavBrand>
		<div class="flex md:order-2">
			<DarkMode class="mx-4">Dark</DarkMode>
			{#if session}
				<SideBar />
				<Button href="/logout" class="mx-3">Logout</Button>
			{:else}
				<Button href="/login" class="mx-3">Login</Button>
			{/if}

			<NavHamburger on:click={toggle} />
		</div>
		<NavUl {hidden} class="order-1">
			<NavLi href="/" active={true}>Accueil</NavLi>
			<NavLi href="/about">A propos</NavLi>
			<NavLi href="/dashboard">Dashboard</NavLi>
			<NavLi href="/sverdle">Sverdle</NavLi>
			<NavLi href="/contact">Contact</NavLi>
		</NavUl>
	</Navbar>
</header>

<style>
</style>
