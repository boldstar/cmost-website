<template>
    <section class="badges">
        <div class="row container mx-auto">
            <div class="row space-around w-100">
                <div class="badges-card">
                    <g-image src="../../static/img/certification1.png"></g-image>
                </div>
                <div class="badges-card">
                    <g-image src="../../static/img/certification2.jpg"></g-image>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
export default {
    name: 'Badges'
}
</script>

<style>
    .badges {
        background: var(--white);
        width: 100%;
        position: relative;
        padding: 35px;
    }

    .badges-card {
        align-self: center;
    }
</style>
