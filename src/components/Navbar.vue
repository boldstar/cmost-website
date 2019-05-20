<template>
    <header class="row">
        <div class="container mx-auto row space-between self-center">
            <a href="/"><img src="../../static/img/logo.png" alt="construction logo" class="logo"></a>
            <nav class="row self-center">
                <g-link class="nav-link" to="/about">About</g-link>
                <g-link class="nav-link" to="/services">Services</g-link>
                <g-link class="nav-link" to="/team">Team</g-link>
                <g-link class="nav-link" to="/projects">Projects</g-link>
                <g-link class="nav-link" to="/">Contact Us</g-link>
            </nav>
        </div>
    </header>
</template>

<script>
export default {
    name: 'Navbar'
}
</script>

<style scoped>
    header{
        width: 100%;
        position: fixed;
        background: var(--dark);
        height: 75px;
        z-index: 100000;
    }

    .logo {
        width: auto;
        height: 50px;
    }

    .nav-link {
        font-size: 1.25rem;
        color: var(--white);
        font-weight: bold;
        margin-left: 35px;
        text-decoration: none;
    }
    
    .nav-link:hover {
        color: var(--main);
    }
</style>
