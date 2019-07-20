<script>
	import LoginContainer from './components/LoginContainer.svelte';
	import { auth } from './stores/security.js'

	let authenticated;
	const listenAuth = auth.subscribe(value => {
        authenticated = value;
    });
</script>

<LoginContainer/>
{#if authenticated}
	<div id="desk">Hello! I'm your desk!</div>
{/if}

<style>
	#desk {
        height: 100%;
        width: 95%;
		background-color: white;
		margin-left: 5%;
		padding: 10px;
		box-sizing: border-box;
    }
</style>