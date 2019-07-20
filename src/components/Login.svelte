<script>
    import { auth } from '../stores/security.js'
    let login = '';
    let pwd = '';

    function handleLogin(event) {
        if(login === 'admin' && pwd === 'admin'){
            auth.set(true);
        }
    }
    let authenticated;
    const listenAuth = auth.subscribe(value => {
        authenticated = value;
    });
</script>

<form on:submit|preventDefault={handleLogin}>
    <h2>Connexion</h2>
    <div>
        <label for="login">Login</label>
        <input bind:value={login} type="text" id="login">
    </div>
    <div>
        <label for="pwd">Password</label>
        <input bind:value={pwd} type="password" id="pwd">
    </div>
    <button type="submit">Se Connecter</button>
</form>