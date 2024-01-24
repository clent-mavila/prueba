<script setup>
import MundoZurichLayout from "@/Layouts/MundoZurichLayout.vue";
import Menu from "@/Components/Menu/Menu.vue";
import Section from "@/Components/Sections/Section.vue";
import { Head } from "@inertiajs/vue3";

const Card_mi_cuenta = [
    {
        imageSrc: "/build/img/user-section.png",
        iconoSrc_user: "/build/img/user.png",
        iconoSrc_rut: "/build/img/rut.png",
        iconoSrc_email: "/build/img/mail-icon.png",
        iconoSrc_fecha: "/build/img/calendar.svg",
        iconoSrc_comuna: "/build/img/location.svg",
        iconoSrc_telefono: "/build/img/phone.svg",
    },
];
const titulo_mi_cuenta_principal = [
    {
        title: "Mi cuenta",
        favoritos: "Favoritos",
        guardados: "Guardados",
        cambiar_clave: "Cambiar clave",
    },
];
const titulo_mi_cuenta = [
    {
        title: "Mi información personal",
    },
];
const titulo_mi_cuenta_favoritos = [
    {
        title: "Mis favoritos ",
    },
];
const titulo_mi_cuenta_guardados = [
    {
        title: "GUARDADOS ",
    },
];
const titulo_info = [
    {
        title: "Para editar todos tus datos, simplemente accede a tu Portal de Clientes o comunícate con nuestro Servicio al Cliente llamando al 600 600 9090.",
    },
];
const card_favoritos_principal = [
    {
        title: "Consulta veterinaria",
        descripcion:
            "Nuestras mascotas son parte de nuestra familia y se merecen lo mejor, por eso traemos un servicio pensado para ellos y su salud, donde podrás agendar una hora online con un veterinario que te ayudara y orientara en consultas en medicina preventiva y conductuales.",
        estado: "Sin costo",
        categoria: "Otros Servicios",
        imageSrc: "/build/img/foto-1.jpg",
    },
    {
        title: "Apoyo escolar online",
        descripcion:
            "Nuestras mascotas son parte de nuestra familia y se merecen lo mejor, por eso traemos un servicio pensado para ellos y su salud, donde podrás agendar una hora online con un veterinario que te ayudara y orientara en consultas en medicina preventiva y conductuales.",
        estado: "Sin costo",
        categoria: "Otros Servicios",
        imageSrc: "/build/img/foto-3.jpg",
    },
    {
        title: "Asesoría legal",
        descripcion:
            "Nuestras mascotas son parte de nuestra familia y se merecen lo mejor, por eso traemos un servicio pensado para ellos y su salud, donde podrás agendar una hora online con un veterinario que te ayudara y orientara en consultas en medicina preventiva y conductuales.",
        estado: "Sin costo",
        categoria: "Otros Servicios",
        imageSrc: "/build/img/foto-2.jpg",
    },
];
const card_guardados_principal = [
    {
        title: "Consulta  guardados",
        descripcion:
            "Nuestras mascotas son parte de nuestra familia y se merecen lo mejor, por eso traemos un servicio pensado para ellos y su salud, donde podrás agendar una hora online con un veterinario que te ayudara y orientara en consultas en medicina preventiva y conductuales.",
        estado: "Sin costo",
        categoria: "Otros Servicios",
        imageSrc: "/build/img/alimento-2.png",
    },
    {
        title: "Apoyo  guardados",
        descripcion:
            "Nuestras mascotas son parte de nuestra familia y se merecen lo mejor, por eso traemos un servicio pensado para ellos y su salud, donde podrás agendar una hora online con un veterinario que te ayudara y orientara en consultas en medicina preventiva y conductuales.",
        estado: "Sin costo",
        categoria: "Otros Servicios",
        imageSrc: "/build/img/alimento-2.png",
    },
    {
        title: "Asesoría legal",
        descripcion:
            "Nuestras mascotas son parte de nuestra familia y se merecen lo mejor, por eso traemos un servicio pensado para ellos y su salud, donde podrás agendar una hora online con un veterinario que te ayudara y orientara en consultas en medicina preventiva y conductuales.",
        estado: "Sin costo",
        categoria: "Otros Servicios",
        imageSrc: "/build/img/alimento-2.png",
    },
];
const card_favoritos = [
    {
        title: "Consulta veterinaria 5",
        descripcion:
            "Nuestras mascotas son parte de nuestra familia y se merecen lo mejor, por eso traemos un servicio pensado para ellos y su salud, donde podrás agendar una hora online con un veterinario que te ayudara y orientara en consultas en medicina preventiva y conductuales.",
        estado: "Sin costo",
        categoria: "Otros Servicios",
        imageSrc: "/build/img/foto-1.jpg",
    },
    {
        title: "Consulta veterinaria 4",
        descripcion:
            "Nuestras mascotas son parte de nuestra familia y se merecen lo mejor, por eso traemos un servicio pensado para ellos y su salud, donde podrás agendar una hora online con un veterinario que te ayudara y orientara en consultas en medicina preventiva y conductuales.",
        estado: "Sin costo",
        categoria: "Otros Servicios",
        imageSrc: "/build/img/foto-1.jpg",
    },
    {
        title: "Consulta veterinaria 1",
        descripcion:
            "Nuestras mascotas son parte de nuestra familia y se merecen lo mejor, por eso traemos un servicio pensado para ellos y su salud, donde podrás agendar una hora online con un veterinario que te ayudara y orientara en consultas en medicina preventiva y conductuales.",
        estado: "Sin costo",
        categoria: "Otros Servicios",
        imageSrc: "/build/img/foto-1.jpg",
    },
    {
        title: "Apoyo escolar online 2",
        descripcion:
            "Nuestras mascotas son parte de nuestra familia y se merecen lo mejor, por eso traemos un servicio pensado para ellos y su salud, donde podrás agendar una hora online con un veterinario que te ayudara y orientara en consultas en medicina preventiva y conductuales.",
        estado: "Sin costo",
        categoria: "Otros Servicios",
        imageSrc: "/build/img/foto-3.jpg",
    },
    {
        title: "Apoyo escolar online 2",
        descripcion:
            "Nuestras mascotas son parte de nuestra familia y se merecen lo mejor, por eso traemos un servicio pensado para ellos y su salud, donde podrás agendar una hora online con un veterinario que te ayudara y orientara en consultas en medicina preventiva y conductuales.",
        estado: "Sin costo",
        categoria: "Otros Servicios",
        imageSrc: "/build/img/foto-3.jpg",
    },
    {
        title: "Apoyo escolar online 2",
        descripcion:
            "Nuestras mascotas son parte de nuestra familia y se merecen lo mejor, por eso traemos un servicio pensado para ellos y su salud, donde podrás agendar una hora online con un veterinario que te ayudara y orientara en consultas en medicina preventiva y conductuales.",
        estado: "Sin costo",
        categoria: "Otros Servicios",
        imageSrc: "/build/img/foto-3.jpg",
    },
];
const card_guardados = [
    {
        title: "Consulta veterinaria ",
        descripcion:
            "Nuestras mascotas son parte de nuestra familia y se merecen lo mejor, por eso traemos un servicio pensado para ellos y su salud, donde podrás agendar una hora online con un veterinario que te ayudara y orientara en consultas en medicina preventiva y conductuales.",
        estado: "Sin costo",
        categoria: "Otros Servicios",
        imageSrc: "/build/img/alimento-2.png",
    },
    {
        title: "Consulta veterinaria ",
        descripcion:
            "Nuestras mascotas son parte de nuestra familia y se merecen lo mejor, por eso traemos un servicio pensado para ellos y su salud, donde podrás agendar una hora online con un veterinario que te ayudara y orientara en consultas en medicina preventiva y conductuales.",
        estado: "Sin costo",
        categoria: "Otros Servicios",
        imageSrc: "/build/img/alimento-2.png",
    },
    {
        title: "Consulta veterinaria ",
        descripcion:
            "Nuestras mascotas son parte de nuestra familia y se merecen lo mejor, por eso traemos un servicio pensado para ellos y su salud, donde podrás agendar una hora online con un veterinario que te ayudara y orientara en consultas en medicina preventiva y conductuales.",
        estado: "Sin costo",
        categoria: "Otros Servicios",
        imageSrc: "/build/img/alimento-2.png",
    },
    {
        title: "Apoyo escolar ",
        descripcion:
            "Nuestras mascotas son parte de nuestra familia y se merecen lo mejor, por eso traemos un servicio pensado para ellos y su salud, donde podrás agendar una hora online con un veterinario que te ayudara y orientara en consultas en medicina preventiva y conductuales.",
        estado: "Sin costo",
        categoria: "Otros Servicios",
        imageSrc: "/build/img/alimento-2.png",
    },
    {
        title: "Apoyo escolar",
        descripcion:
            "Nuestras mascotas son parte de nuestra familia y se merecen lo mejor, por eso traemos un servicio pensado para ellos y su salud, donde podrás agendar una hora online con un veterinario que te ayudara y orientara en consultas en medicina preventiva y conductuales.",
        estado: "Sin costo",
        categoria: "Otros Servicios",
        imageSrc: "/build/img/alimento-2.png",
    },
    {
        title: "Apoyo escolar",
        descripcion:
            "Nuestras mascotas son parte de nuestra familia y se merecen lo mejor, por eso traemos un servicio pensado para ellos y su salud, donde podrás agendar una hora online con un veterinario que te ayudara y orientara en consultas en medicina preventiva y conductuales.",
        estado: "Sin costo",
        categoria: "Otros Servicios",
        imageSrc: "/build/img/alimento-2.png",
    },
];
defineProps({
    user: {
        type: Object,
        default: null,
    },
});
</script>

<template>
    <Head title="Mi Cuenta" />
    <MundoZurichLayout>
        <Menu :showTitle="false" />
        <!-- TITULO DE SECCIÓN -->
        <Section
            section="MI-CUENTA_PRINCIPAL"
            estilo="section-title "
            :tituloSection="titulo_mi_cuenta_principal"
        />
        <Section
            section="MI-CUENTA"
            estilo="section-destacados "
            :tituloSection="titulo_mi_cuenta"
            :objetocard="Card_mi_cuenta"
            :user="user"
        />

        <Section
            section="MI_CUENTA_INFO"
            estilo="section-destacados "
            :tituloSection="titulo_info"
        />

        <Section
            section="MI-CUENTA-FAVORITOS"
            estilo="section-destacados "
            :tituloSection="titulo_mi_cuenta_favoritos"
            :objetocard_2="card_favoritos_principal"
            :objetocard="card_favoritos"
            v-bind:verMas="verMas"
            v-bind:cardsVisibles="cardsVisibles"
        />
        <Section
            section="MI-CUENTA-GUARDADOS"
            estilo="section-destacados "
            :tituloSection="titulo_mi_cuenta_guardados"
            :objetocard_2="card_guardados_principal"
            :objetocard="card_guardados"
            v-bind:verMas="verMas"
            v-bind:cardsVisibles="cardsVisibles"
        />
    </MundoZurichLayout>
</template>

<script>
export default {
    data() {
        return {
            verMas: false,
            cardsVisibles: 7,
        };
    },
};
</script>
