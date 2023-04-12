<script>
	import { page } from '$app/stores';
	import Header from './Header.svelte';
	import logo from '$lib/images/logo_fynx.png';
	import ChartLine from 'svelte-material-icons/ChartLine.svelte';
	import SyncCircle from 'svelte-material-icons/SyncCircle.svelte';
	import SwapHorizontalBold from 'svelte-material-icons/SwapHorizontalBold.svelte';
	import MessageText from 'svelte-material-icons/MessageText.svelte';
	import AccountCheck from 'svelte-material-icons/AccountCheck.svelte';
	import CogOutline from 'svelte-material-icons/CogOutline.svelte';
	import './styles.css';
	const routesDirArr = ['Chart', 'Market', 'Exch', 'Board', 'Office', 'Sys'];
</script>

<div id="site-wrap">
	<nav>
		<div id="logo-box">
			<a href="/">
				<img src={logo} alt="logo" />
			</a>
		</div>
		<div id="menu-box">
			{#each routesDirArr as routesDir, i}
				<li>
					<a
						class={$page.url.pathname === '/' + routesDir.toLowerCase() ? 'current' : undefined}
						href="/{routesDir === 'Chart' ? '' : routesDir.toLowerCase()}"
					>
						<div class="path_name-box">
							{#if i === 0}
								<ChartLine />
							{:else if i === 1}
								<SwapHorizontalBold />
							{:else if i === 2}
								<SyncCircle />
							{:else if i === 3}
								<MessageText />
							{:else if i === 4}
								<AccountCheck />
							{:else if i === 5}
								<CogOutline />
							{/if}
							<span class="path_name">{routesDir}</span>
						</div>
					</a>
				</li>
			{/each}
		</div>
	</nav>
	<main>
		<Header />
		<div class="container">
			<slot />
		</div>
		<footer>CopyRight &copy; 2022 FYNX</footer>
	</main>
</div>

<style>
	#site-wrap {
		max-width: 1020px;
		width: 100vw;
		margin: 0 auto;
		min-height: 100vh;
		position: relative;
		display: flex;
		justify-content: space-between;
		align-items: stretch;
	}
	main {
		flex-grow: 1;
		min-height: 100%;
		padding-bottom: 60px;
		background: var(--main-color);
		position: relative;
	}
	.container {
		padding: 15px;
		padding-bottom: 50px;
	}
	nav {
		min-width: 220px;
		min-height: 100%;
		border-right: solid var(--nav-border-color) 1px;
		padding-left: 10px;
	} /**background: var(--nav-color);*/
	#logo-box {
		text-align: center;
		padding: 35px 0;
	}
	#logo-box img {
		width: 160px;
	}
	#menu-box {
		position: sticky;
		top: 0px;
	}
	#menu-box li {
		position: relative;
		list-style-type: none;
	}
	#menu-box li a {
		display: block;
		height: 50px;
		line-height: 50px;
		padding-right: 15px;
		text-align: right;
		color: #d1d1d1;
		border-radius: 25px 0 0 25px;
	}
	#menu-box li a:hover {
		text-decoration: none;
		background: rgba(73, 73, 245, 0.3);
		color: #fff;
	}
	#menu-box li a.current {
		background: var(--header-color);
		color: #fff;
	}
	#menu-box li .path_name-box {
		display: flex;
		justify-content: space-between;
		align-items: center;
		padding-left: 15px;
		font-size: 2rem;
	}
	.path_name-box .path_name {
		font-size: 1.5rem;
	}
	footer {
		position: absolute;
		bottom: 0;
		left: 0;
		right: 0;
		background: var(--footer-color);
		height: 50px;
		padding: 15px;
		color: #d1d1d1;
	}

	/* Extra small devices (portrait phones, less than 360px) */
	@media (max-width: 369.98px) {
		/* .footer-menu-box .menu-li-mo .bi {font-size:1rem;} */
		/* .footer-menu-box .menu-li-mo span {font-size:0.7rem;} */
	}

	/* Extra small devices (portrait phones, less than 576px) */
	@media (max-width: 505.98px) {
		/* .icon_security {width:15px;} */
		/* .coin-box .it_name {letter-spacing: -0.1rem;} */
		/* .footer-menu-box .menu-li-mo {padding-top:20px;} */
		/* .footer-menu-box .menu-li-mo span {font-size:0.7rem;} */
	}

	/* Extra small devices (portrait phones, less than 576px) */
	@media (max-width: 575.98px) {
	}

	/* Small devices (landscape phones, less than 768px) */
	@media (max-width: 767.98px) {
		/* #header-box #logo-img {visibility: visible;} */
		nav {
			display: none;
		}
		/* #footer-box {visibility: visible;} */
	}

	/* Medium devices (tablets, less than 992px) */
	@media (min-width: 768px) and (max-width: 991.98px) {
	}

	@media (max-width: 1020.98px) {
		/* nav {left:0px;margin-left:0;padding-bottom:100px;} */
	}
</style>
