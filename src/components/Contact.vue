<template>
    <section class="contact">
        <div class="content-column">
            <h2 class="contact-header">Contact Us</h2>
            <div class="row space-around w-100 container">
                <Map />
                <Form />
            </div>
        </div>
    </section>
</template>

<script>
import Map from '~/components/Map.vue'
import Form from '~/components/Form.vue'
export default {
 name: 'Contact',
 components: {
     Map,
     Form
 }
}
</script>

<style>
    .contact {
        background: var(--dark);
        width: 100%;
        position: relative;
        padding: 35px;
        margin-bottom: 50px;
    }

    .contact-header {
        font-size: 2rem;
        font-weight: bold;
        border-bottom: 5px solid var(--main);
        margin-top: 10px;
        margin-bottom: 50px;
    }

</style>
