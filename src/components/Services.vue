<template>
    <section class="services">
        <div class="content-column container mx-auto">
            <h2 class="services-header">Services</h2>
            <div class="content-row service-cards">
                <div class="services-card">
                    <h2 class="services-card-header">Commercial</h2>
                    <img src="../../static/img/commercial_building.png" alt="commercial construction" class="service-img">
                    <button class="service-btn">Learn More</button>
                </div>
                <div class="services-card">
                    <h2 class="services-card-header">Institutional</h2>
                    <img src="../../static/img/institutional_building.png" alt="institutional construction" class="service-img">
                    <button class="service-btn">Learn More</button>
                </div>
                <div class="services-card">
                    <h2 class="services-card-header">Industrial</h2>
                    <img src="../../static/img/industrial_building.png" alt="industrial construction" class="service-img">
                    <button class="service-btn">Learn More</button> 
                </div>
            </div>
        </div>
    </section>
</template>

<script>
export default {

}
</script>

<style>
.services {
    background: var(--main);
    width: 100%;
    position: relative;
    height: 500px;
}

.services-header {
    font-size: 2rem;
    font-weight: bold;
    border-bottom: 5px solid var(--black);
    margin: 10px;
}

.service-cards {
    margin-top: 25px;
}

.services-card {
    height: 300px;
    width: 300px;
    position: relative;
    background: var(--dark);
    color: var(--white);
    text-align: center;
    border-radius: 5px;
    transition: all .2s linear;
    margin-top: 5px;
}

.services-card:hover {
    box-shadow: 0 0 10px 0 rgba(0,0,0,.5);
    margin-top: 0;
}

.services-card-header {
    margin-top: 15px;
    margin-bottom: 5px;
}

.service-img {
    margin-top: 10px;
    object-fit: cover;
    width: 300px;
    border-radius: 0 0 5px 5px;
    cursor: pointer;
    transition: all .2s linear;
}

.service-img:hover {
    opacity: .8;
}

.services-card .service-btn {
    visibility: hidden;
    position: absolute;
    bottom: 20px;
    left: 34%;
    cursor: pointer;
    font-size: 1rem;
    font-weight: bold;
    border-radius: 2px;
    padding: 5px 10px;
    border: none;
    background: var(--white);
    color: var(--main);
}

.services-card:hover .service-btn {
    visibility: visible;
}


</style>
