<template>
    <section class="mission">
        <div class="content-column container mx-auto">
            <h2 class="mission-header">Our Mission</h2>
            <p class="mission-slogan">Construction Managers of Southeast Texas (CMOST) mission is to continue being the best general contracting firm in our area by utilizing our diverse experience. Our experience in construction management, subcontracting, and accelerated project completion is the reason we are successful. We always keep you involved, satisfied, and on schedule.</p>
        </div>
        <img src="../../static/img/construction_blueprints.png" class="mission-blueprint" alt="construction image blueprint">
    </section>
</template>

<script>

export default {
    name: 'Mission',
}
</script>

<style>
.mission {
    background: var(--black);
    position: relative;
    bottom: -150px;
}
.mission-header {
    font-size: 2rem;
    font-weight: bold;
    border-bottom: 5px solid var(--main);
    margin: 10px;
}

.mission-slogan {
    text-align: center;
    max-width: 600px;
    margin: 0 auto;
    font-size: 1.25rem;
    z-index: 1;
}

.mission-blueprint {
    position: relative;
    left: 0;
    top: -150px;
    width: 100%;
    background: var(--black);
    z-index: 0;
}

</style>
