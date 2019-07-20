<script>
    import { auth } from '../stores/security.js'
    
    function handleLogout() {
        auth.set(false);
    }
</script>

<style>
    button {
        padding: 10px;
    }
</style>

<button on:click={handleLogout}>Bye!</button>