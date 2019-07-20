<script>
    import Login from './Login.svelte'
	import Logout from './Logout.svelte'
    import { auth } from '../stores/security.js'

	let authenticated;
	const listenAuth = auth.subscribe(value => {
        authenticated = value;
    });
</script>

<style>
    #container {
        box-shadow: 5px 10px 8px #888888;
        transition-duration: 0.5s;
    }

    #container.connected {
        position: absolute;
        top: 0;
        bottom: 0;
        left: 0;
        width: 5%;
        text-align: center;
        background: linear-gradient(to right, lightgrey 20% , white 50%, lightgrey);
        box-shadow: 5px 0px 8px #888888;
    }

    #container.disconnected {
        padding: 1rem;
        width: 15rem;
        border-radius: 15px;
        overflow: hidden;
    }
</style>

<div id="container" class:connected="{authenticated}" class:disconnected="{!authenticated}">
    {#if !authenticated}
	<Login/>
    {:else}
    <Logout/>
    {/if}
</div>
