<template>
    <footer>
        <div class="content-row container mx-auto footer-contents">
            <p class="footer-copy">&copy;2019 Sitebox Designs | All Rights Reserved</p>
        </div>
    </footer>
</template>

<script>
export default {
    name: 'Footer'
}
</script>

<style>
footer {
    width: 100%;
    background: var(--main);
    height: 100px;
    position: relative;
}

.footer-contents {
    height: 100%;
}

.footer-copy {
    font-size: 1.5rem;
    align-self: center;
}
</style>
